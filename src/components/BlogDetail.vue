<template>

    <div class="">
        <div class="vic__new__post__button__section" v-if="createNewBtn">
            <button class="vic__blog__action__button__create" v-on:click="() => showForm('create')">New Post</button>
            <button class="vic__blog__action__button__back" v-on:click="() => showForm('back')">Back</button>
        </div>
        <component v-bind:is="component" :callback="showDetail" :detailData="detailData" :updateData="updateData"
            :showForm="showForm" :createBlogData="createBlogData" :updateBlogData="updateBlogData"
            :deleteBlogData="deleteBlogData" />
    </div>
</template>

<script>
import BlogList from './BlogList.vue'
import DetailCard from './DetailCard.vue'
import BlogForm from './BlogForm.vue'
export default {
    name: "BlogDetail",
    props: ["detailData"],
    components: {
        DetailCard,
        BlogList,
        BlogForm
    },
    data() {
        return {
            component: "DetailCard",
            updateData: this.detailData,
            createNewBtn: true,
            formData: {}
        }
    },
    created() {
        this.createBlogData();
        this.updateBlogData();
        this.deleteBlogData();
        this.showDetail();
        this.showForm();
    },
    methods: {
        createBlogData() {
            fetch(`https://jsonplaceholder.typicode.com/posts${this.detailData.id}`, {
                method: 'PUT',
                body: JSON.stringify(this.formData),
                headers: {
                    "Content-type": "application/json; charset=UTF-8"
                }
            })
                .then(response => response.json())
                .then(json => console.log(json))

        },
        updateBlogData() {
            fetch(`https://jsonplaceholder.typicode.com/posts${this.detailData.id}`, {
                method: 'PUT',
                body: JSON.stringify(this.formData),
                headers: {
                    "Content-type": "application/json; charset=UTF-8"
                }
            })
                .then(response => response.json())
                .then(json => console.log(json))

        },
        deleteBlogData() {
            fetch(`https://jsonplaceholder.typicode.com/posts/${this.detailData.id}`, {
                method: 'DELETE'
            })
                .then(response => response.json())
                .then(json => console.log(json))
        },
        showForm(getPage) {
            if (getPage === 'detail') {
                this.component = DetailCard;
                this.createNewBtn = true;
            } else if (getPage === 'create') {
                this.component = BlogForm;
                this.createNewBtn = false;
                this.updateData = {}
            }
            else if (getPage === 'update') {
                this.component = BlogForm;
                this.createNewBtn = false;
                this.updateData = this.detailData;
            } else if (getPage === 'list') {
                this.component = BlogList;
                this.createNewBtn = false;
            }
            else {
                this.component = DetailCard;
            }
        }
    },
};
</script>