<script setup>
const props = defineProps(['title', 'comment']);
</script>

<template> 
    <div class="centrer2">
            <li>
                <h2>{{ title }}</h2>
                <p>{{ comment }}</p>
            </li>
    </div>
</template>

<style>

.centrer2{
    text-align: center;
}
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