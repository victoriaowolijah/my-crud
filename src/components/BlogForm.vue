<template>
    <div class="vic__container">
        <div class="vic__new__post__button__section">
            <button class="vic__blog__close__form" v-on:click="() => handleSwitch('detail')">close form</button>
        </div>
        <div class="vic__row">
            <div class="vic__col_1">
                <h1 class="vic__form__title">Created Blog post </h1>
                <div class="my-form">
                    <form class="vic__form">
                        <div class="form__section">
                            <div class="form__group">
                                <label class="form__label">Blog Tile
                                    <input class="form__control" type="text" name="blog_title" placeholder="blog title"
                                        required v-model="formData.title" />
                                </label>
                            </div>
                            <div class="form__group">
                                <label class="form__label">Blog Content
                                    <textarea required rows="10" class="form__control" type="text" name="blog_content"
                                        placeholder="content" v-model="formData.body"></textarea> </label>
                            </div>

                            <div class="form__group">
                                <div class="form__button_section">
                                    <button class="form__button" type="submit">Post</button>
                                </div>
                            </div>
                        </div>
                    </form>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: "BlogForm",
    props: ["updateData", "createBlogData", "updateBlogData", "deleteBlogData", "showForm"],
    data() {
        return {
            formData: {
                id: this.updateData.id ? this.updateData.id : "",
                title: this.updateData.title ? this.updateData.title : "",
                body: this.updateData.body ? this.updateData.body : ''
            }
        }
    },
    methods: {
        handleSwitch(info) {
            this.showForm(info)
        },
        handleCreateBlog() {
            const blogTitle = document.querySelector('input[name="blog_title"]').value;
            const blogContent = document.querySelector('textarea[name="blog_content"]').value;
            const data = {
                title: blogTitle,
                body: blogContent
            }
            this.createBlogData(data)
        },
        handleUpdateBlog() {
            const blogTitle = document.querySelector('input[name="blog_title"]').value;
            const blogContent = document.querySelector('textarea[name="blog_content"]').value;
            const data = {
                id: this.formData.id,
                title: blogTitle,
                body: blogContent
            }
            this.updateBlogData(data)
        },
        handleDeleteBlog() {
            const data = {
                id: this.formData.id
            }
            this.deleteBlogData(data)
        }
    }
};
</script>

<style scoped>

</style>