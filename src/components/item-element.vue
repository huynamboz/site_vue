<template>
    <div class="item-list">
        <p>{{item}}</p>
    </div>
</template>

<script>
export default {
    props: {
        item: String
    }
}
</script>

<style scoped>
p{
    margin: 0px;
}
.item-list{
    background-color: #ffd6d6;
    min-width: 50px;
    display: inline-block;
    padding: 10px 20px;
    border-radius: 8px;
    margin: 10px 10px 0px 10px;

}
</style>