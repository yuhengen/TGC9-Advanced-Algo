<template>
    <div>
        <ul>
            <li v-for='(item, index) in queue.getItems()' v-bind:key='index'>
                {{item}}
            </li>
        </ul>
        <input type="text" v-model="newItem"/><br/>
        <textarea v-model='log'></textarea>
        <button @click="addToQueue">Enqueue</button>
        <button @click="processQueue">Dequeue next</button>
    </div>
</template>

<script>
import Queue from '../data-structures/Queue';
export default {
    data:function(){
        return {
            queue: new Queue(),
            newItem:'',
            log:''
        }
    },
    mounted:function(){
        setInterval(this.processQueue, 3000);
    },
    methods:{
        addToQueue:function(){
            this.queue.enqueue(this.newItem);
        },
        processQueue:function(){
            if (this.queue.peek()) {
                 let itemToProcess = this.queue.dequeue();
                 this.log += "Processing " + itemToProcess + "\n";
                //  alert("Processing " + itemToProcess);
            }
    
        }
    }
}
</script>

<style scoped>
li {
    display:inline-block;
    width: 50px;
    height: 50px;
    margin:10px;
    padding:10px;
    text-align:center;
    border: 1px solid black;
}
</style>