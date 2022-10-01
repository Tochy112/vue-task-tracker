<template>
    <button @click="onClick" :style="{backgroundColor: color}" class="btn">{{text}}</button>
</template>

<script>
    export default {
        name: "Button",
        props: {
            text: String,
            color: String
        },
          
        methods: {
            onClick(){
                this.$emit('btn-click')
            },
        }
    }
</script>

<style scoped>
.btn{
  border-radius: 5px;
  padding: 15px;
  color: #fff;
  background-color: #000;
  cursor: pointer;
  font-size: large;
}


</style>