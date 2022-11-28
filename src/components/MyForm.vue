<template>
    <div class="vic__container">
        <div class="vic__row">
            <div class="vic__col_1">
                <h1 class="vic__form__title">Form Title </h1>
                <div class="my-form">
                    <form class="vic__form">
                        <div class="form__section">
                            <div class="form__group">
                                <label class="form__label">First Name
                                    <input class="form__control" type="text" name="First_name"
                                        placeholder="First Name" />
                                </label>
                            </div>
                            <div class="form__group">
                                <label class="form__label">Last Name
                                    <input class="form__control" type="text" name="last_name" placeholder="Last Name" />
                                </label>
                            </div>
                            <div class="form__group">
                                <label class="form__label">email
                                    <input class="form__control" type="email" name="email"
                                        placeholder="email@example.com" />
                                </label>
                            </div>
                            <div class="form__group">
                                <div class="form__button_section">
                                    <button class="form__button" type="submit">Submit</button>
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
    name: "MyForm"
};
</script>

<style scoped>

</style>