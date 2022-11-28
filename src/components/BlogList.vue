<template>
    <div class="vic__blog__section">
        <h1 class="vic__blog__page__header" v-if="currentPage">
            Browse Blog
        </h1>
        <div class="">
            <component v-bind:is="component" :callback="showDetail" :detailData="detailData" />
        </div>
    </div>
</template>

<script>
import BlogDetail from './BlogDetail.vue'
import BlogCard from './BlogCard.vue'

export default {
    name: "BlogList",
    components: {
        BlogCard,
        BlogDetail
    },
    data() {
        return {
            component: "BlogCard",
            detailData: {},
            currentPage: true
        }
    },
    methods: {
        showDetail(data) {
            if (this.component === 'BlogCard') {
                this.component = BlogDetail;
                this.currentPage = false;
                this.detailData = data
                console.log(data)
            }
        }
    },

};
</script>