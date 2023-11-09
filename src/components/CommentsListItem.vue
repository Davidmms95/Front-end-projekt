<script setup>
const props = defineProps(['title', 'comment']);
</script>

<template> 
            <li>
                <h2>{{ title }}</h2>
                <p>{{ comment }}</p>
            </li>
</template>

<style>

li{
    list-style-type: none;
}

h2{
  width: 300px;
  height: 25px;
  border: 1px solid black;
}

p{

  width: 300px;
  height: 100px;
  border: 1px solid black;
}


</style>