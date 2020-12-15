<template>
    <div id="container">
        <div>
            <ul style="display:flex;flex-direction:column-reverse">
                <li v-for='(item, index) in stack.getItems()' v-bind:key="index">
                    {{item}}
                </li>
            </ul>
        </div>
        <div>
            <input type="text" v-model="newItem"/>
            <button @click="doPush">Push</button>
            <button @click="doPop">Pop</button>
        </div>
    </div>
</template>

<script>
import Stack from '../data-structures/Stack';
export default {
    data:function(){
        return {
            stack: new Stack(),
            newItem:''
        }
    },
    methods:{
        doPush:function(){
            this.stack.push(this.newItem);
        },
        doPop:function(){
            let popped = this.stack.pop();
            alert(popped);
        }
    }
}
</script>

<style scoped>
#container{
    display:flex;
    justify-content: space-around;
}
li {
    height: 50px;
    width: 50px;
    list-style-type:none;
    border:1px solid black;
    text-align:center;
}
</style>