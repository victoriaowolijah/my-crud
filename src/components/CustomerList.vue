<template>
    <div class="vic__container">
        <div class="vic__row">
            <div class="vic__col__2">

                <table class="vic__table__group">
                    <h1 class="vic__table__title">Table Title </h1>
                    <thread class="vic__table__head">
                        <tr class="vic__table__row">
                            <th class="vic__table__item__sn">S/N</th>
                            <th class="vic__table__item_name">Name</th>
                            <th class="vic__table__item_email">E-mail</th>
                            <th class="vic__table__item__action">Action</th>
                        </tr>
                    </thread>

                    <tbody class="vic__table__body">
                        <tr class="vic__table__row">
                            <td class="vic__table__item__sn">1</td>
                            <td class="vic__table__item_name">victoria Sonny Owolijah</td>
                            <td class="vic__table__item_email">victoria@sonny.com</td>
                            <td class="vic__table__item__action">
                                <div class="vic__table__row">
                                    <div class="vic__table__action__row">
                                        <button id="vic__table__action__button__edit">Edit</button>
                                        <button id="vic__table__action__button__delete">Delete</button>
                                    </div>
                                </div>
                            </td>
                        </tr>
                    </tbody>
                </table>
            </div>
        </div>
    </div>









</template>

<script>
export default {
    name: "CustomerList"
};


</script>

<style >

</style>