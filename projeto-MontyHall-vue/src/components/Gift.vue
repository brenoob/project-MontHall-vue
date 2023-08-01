<template>
  <div class="gift">
    <div class="gift-tie-1"></div>
    <div class="gift-tie-2"></div>
    <div class="gift-top"></div>
    <div class="gift-body"></div>
  </div>
</template>

<script>
export default{
  name:'Gift'
}
</script>

<style>
/* gift presente */
.gift{
  position: relative;
  display: flex;
  flex-direction: column;
  align-items: center;
  z-index: 10;
}
.gift-top{
  width: 6.25rem;
  height: 1.563rem;
  background-color: #7aa944;
}
.gift-body{
  width: 5.625rem;
  height: 3.75rem;
  background-color: #5c7e32;
}
.gift-tie-1{
  position: absolute;
  width: 0.938rem;
  height: 5.3rem;
  background-color: red;
}
.gift-tie-2{
  position: absolute;
  width: 5.625rem;
  height: 0.938rem;
  top: 2.5rem;
  background-color: red;
}
</style>