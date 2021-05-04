<template>
    <div class="todoListContainer">
        <div class="heading">
            <h2 id="title">
                Vue Todo List 
            </h2>
            <add-item />
            <item-list 
                :items="items"
            />
        </div>
    </div>
</template>

<script>

import AddItem from './addItem.vue'
import ItemList from './itemList.vue'
export default {
    components:{
        AddItem,
        ItemList
    },

    data: {
        return() {
            items:[]
        }
    },
    methods: {
        getList() {
            axios.get('api/items')
            .then(response => {
                
                this.items =response.data;
                
            })
            .catch(error =>{
                console.log(error);
            })
        }
    },
    created(){
        this.getList();
    }
}
</script>

<style scoped>
.todoListContainer {
    width: 350px;
    margin: auto;
}

.heading{
    background: #e6e6e6;
    padding: 10%;
}
#title{
    text-align: center;
}
</style>