<template>
    <div class="footer">
      <h6>Vue JS is very hard</h6>
      <i class="fab fa-vuejs"></i>
    </div>
</template>

<script>
export default {
  name: "Footer"
}
</script>

<style scoped>
.footer{
  position: fixed;
  z-index: -1;
  display: flex;
  justify-content: center;
  left: 0;
  bottom: 0;
  width: 100%;
  background: #175676;
  padding-top: 15px;
  font-family: "Bebas Neue";
  letter-spacing: 5px;
  color: #cce6f4;
}
.fab{
  color: white;
  padding-left: 10px;
}
</style>