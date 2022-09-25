<template>
  <li>
      <img src="https://cdn-icons-png.flaticon.com/512/706/706807.png">
      <hr>
      <slot name="card-header"> </slot>
      <slot name="card-botton"> </slot>
      <slot name="card-content"> </slot>
  </li>
</template>

<script>
export default {
    name: "Card"
}
</script>

<style scoped>
 li {
  margin: 1rem 0;
  font-size: 1.25rem;
  font-weight: bold;
  background: purple;
  padding: 0.5rem;
  color: white;
  border-radius: 25px;
}
img{
    width: 150px;
    height: 150px;
}
</style>