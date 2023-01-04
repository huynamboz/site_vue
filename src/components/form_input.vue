<template>
<!-- make div class container have input -->
    <div class="container">
        <input type="text" v-model="value" placeholder="this.placehoder">
        <button @click="getData()">ADD</button>
        <div class="box-item" >
            <div class="item" v-for="(item,index) in listItem" :key="item.id" >
        <itemT :item="item">
        </itemT> <div class="del" @click="delItem(index)">x</div>
    </div>
    </div>
    </div>
</template>

<script>
import itemT  from './item-element.vue';
export default {
//import component item
    name: 'form_input',
    components: {
        itemT
    },
    props: {
        placehoder: String
    },
    data(){
        return{
            value:'',
            listItem:[]
        }
    },
    mounted(){
        if(localStorage.storedData){
            this.listItem = localStorage.storedData.split(',');
            
        }
        console.log(this.listItem);
        
    },
    methods:{
        getData(){
            if(this.value == ''){
                alert('please enter value');
                return;
            }
            this.listItem.push(
                this.value
            );
            console.log(this.listItem);
            localStorage.storedData = this.listItem;
        },
        delItem(id){
            console.log(id);
            this.listItem.splice(id,1);
            localStorage.removeItem('storedData');
            localStorage.storedData = this.listItem;
        }
    }
}
</script>
<style lang="scss" scoped>
button{
    margin-top: 10px;
    width: 178px;
    border: none;
    border-radius: 8px;
    color: aliceblue;
    background-color: rgb(210, 162, 254);
    padding: 10px 20px;
    &:hover{
        background-color: rgb(210, 162, 254);
        opacity: 0.8;
    }
}
input{
    padding: 8px 5px;
    border-radius: 8px;
    border: none;
    background-color: antiquewhite;
}
.container{
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
}
.box-item{
    display: flex;
    flex-direction: row;
    justify-content: center;
    width: 400px;
    flex-wrap: wrap;
}
.item{
    position: relative;
}
.del{
    position: absolute;
    top: 10px;
    right: 14px;
    &:hover{
        cursor: pointer;
    }
}
</style>

