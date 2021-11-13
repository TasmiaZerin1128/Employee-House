<template>
  <button :style="{background:colour}" class="btn">{{text}}</button>
</template>

<script>
export default {
  name: "Button",
  props:{
    text: String,
    colour: String
  }
}
</script>

<style scoped>
.btn {
  font-family: Nunito;
  width: 150px;
  height: 40px;
  color: #fff;
  border: none;
  margin: 2px;
  border-radius: 15px;
  cursor: pointer;
  text-decoration: none;
  font-size: 15px;
  margin-left: 100px;
}

</style>