<template>
    <div>
        <div v-for="(item, index) in items" :key="index">
            <listItem
                :item = "ïtem"
                class="item"
            />
        </div>
    </div>
</template>

<script>
import listItem from "./item"
export default {
    props:['item']
}
</script>

<style scoped>
.item{
    background: #e6e6e6;
    padding: 5px;
    margin-top: 5px;
}
</style>