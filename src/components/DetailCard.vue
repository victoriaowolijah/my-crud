<template>
    <div class="vic__blog__detail__section">
        <h1 class="vic__blog__detail__page__header">
            {{ details.title }}
        </h1>
        <div class="vic__blog__detail__row">
            <div class="vic__blog__detail__card">
                <div class="vic__blog__detail__body">
                    <p class="vic__blog__detail__body__text">{{ details.body }}</p>
                </div>
            </div>
            <div class="vic__blog__action">
                <div class="vic__blog__action__button">
                    <button class="vic__blog__action__button__edit"
                        v-on:click="() => handleSwitch('update')">Edit</button>
                    <button class="vic__blog__action__button__delete"
                        v-on:click="() => handleSwitch('update')">Delete</button>
                </div>
            </div>


        </div>
    </div>
</template>

<script>

export default {
    name: "BlogCard",
    props: ["detailData", "showForm", "deleteBlogData"],
    data() {
        return {
            details: {
                id: this.detailData.id,
                title: this.detailData.title,
                body: this.detailData.body
            },
            formData: {}
        }
    },

    methods: {
        handleSwitch(info) {
            this.showForm(info)
        },
        handleDeleteBlog() {
            const data = {
                id: this.formData.id
            }
            this.deleteBlogData(data)
        }

    },
};
</script>