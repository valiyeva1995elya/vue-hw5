<script>
export default {
    data() {
        return {
            text: "",
            percent: "",
            arr: []
        };
    },
    methods: {
        addComp() {
            this.$emit("arr", {
                id: this.arr.length + 1,
                text: this.text,
                percent: this.percent
            })
            this.text = "",
            this.percent = ""
        }
    },
    
}

</script>

<template>
    <div class="block-add">
        <input type="text" placeholder="text" v-model="text"><br>
        <input type="number" placeholder="percent" v-model="percent"><br>
        <button @click="addComp">Add</button>
    </div>
</template>

<style>
input{
    width: 150px;
    height: 20px;
    margin-bottom: 30px;
    background-color: blue;
    color: white;
    border-radius: 5px;
}
button{
    width:160px;
    height: 25px;
    margin-bottom: 30px;
    background-color: blue;
    color: white;
    border-radius: 5px;

}
</style>