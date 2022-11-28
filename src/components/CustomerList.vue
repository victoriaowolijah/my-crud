<template>
    <div class="customer-list">
        <div class="data" style="border: 20px solid blue">
            <table class="ui celled table" style="color:red;   border: 2px solid red">
                <thread style="border: 2px solid green">
                    <tr style="border: 2px solid blue">
                        <th style="width: 50px; text-align: center;">#</th>
                        <th>Name</th>
                        <th>E-mail</th>
                        <th style="width: 148px;">Action</th>
                    </tr>
                </thread>
                
                <tbody style="border: 20px solid blue">
                    <tr>
                        <td>AA</td>
                        <td>BB</td>
                        <td>CC</td>
                        <td>
                            <button class="mini ui blue button">Edit</button>
                            <button class="mini ui red button">Delete</button>
                        </td>
                    </tr>
                </tbody>

            </table>

            
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