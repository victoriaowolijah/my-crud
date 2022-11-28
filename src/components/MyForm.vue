<template>
    <div class="my-form">
        <form class="ui form">
            <div class="fields">
                <div class="four wild field">
                    <label>First Name</label>
                    <input type="text" name="First_name" placeholder="First Name"/>
                </div>
                
                <div class="four wide field">
                    <label>Last name</label>
                    <input type="text" name="last_name" placeholder="Last Name"/>
                </div>

                <div class="six  wide field">
                    <label>E-mail</label>
                    <input type="email" name="Doe@gmailcom" placeholder="Last Name"/>
                </div>
                
                <div class="two side field">
                    <button class="ui primary button submit-button">Save</button>
                </div>
            </div>
        </form>
    </div>
</template>

<script>
export default {
    name: "MyForm"
};
</script>

<style scoped>
</style>