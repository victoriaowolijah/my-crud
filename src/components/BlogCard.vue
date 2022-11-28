<template>
    <div class="vic__blog__row">
        <div class="vic__blog__card" v-for="blog in BlogData" v-bind:key="blog.id">
            <div class="vic__blog__title">
                <h3 class="vic__blog__title__text">{{ blog.title }}</h3>
            </div>
            <div class="vic__blog__body">
                <p class="vic__blog__body__text">{{ blog.body | truncate(100, '...') }}
                    <button class="vic__blog__link" @click="() => handleDetail(blog.id, blog.title, blog.body)">see more
                    </button>
                </p>
            </div>
        </div>
    </div>
</template>

<script>

export default {
    name: "BlogCard",
    props: ["callback"],
    data() {
        return {
            BlogData: []
        }
    },
    created() {
        this.getBlogData();
    },
    methods: {
        getBlogData() {
            fetch('https://jsonplaceholder.typicode.com/posts')
                .then(response => response.json())
                .then(json => {
                    this.BlogData = json;
                })
        },
        handleDetail(id, title, body) {
            const data = {
                id: id,
                title: title,
                body: body
            }
            this.callback(data)
        },
    },
    filters: {
        truncate: function (text, length, suffix) {
            if (text.length > length) {
                return text.substring(0, length) + suffix;
            } else {
                return text;
            }
        }
    }
};
</script>