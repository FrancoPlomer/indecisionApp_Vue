<template>
    <h2>{{ title }}</h2>
    <p>{{ counter }}</p>
    <div>
        <button @click="increased()">+1</button>
        <button @click="decreased()">-1</button>
    </div>
</template>
<script>
    export default {
        name: "Counter",
        data() {
        return{
            counter: this.start,
            }
        },
        props: {
            title:{
                type: String,
                default: "Counter"
            },
            start:{
                type: Number,
                required: true,
                validator( value ){
                    return value >= 0;
                }
            }
        },
        methods: {
            increased(){
                this.counter += 1
            },
            decreased(){
                this.counter -= 1
            }
        },
        computed: {

        },
}

</script>
<style>

</style>