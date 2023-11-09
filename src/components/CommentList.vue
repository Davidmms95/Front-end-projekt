<script setup>
import {
    onMounted,
    ref
} from 'vue';
import CommentsListItem from './CommentsListItem.vue';
import CreateComment from './CreateComment.vue'

const comments = ref({});

onMounted(() =>{
    getComments();
})

const getComments = () => {   
    fetch('https://kommentar-7811a-default-rtdb.europe-west1.firebasedatabase.app/kommentar.json', {
        method: 'GET'
    })
    .then((res) => res.json())
    .then((res) => {
        console.log(res);
        comments.value=res;
    });
};
</script>

<template>
    <div class="centrer">
        <CreateComment 
            v-on:submitted="getComments"
        />
        <hr>
        <ul>
            <CommentsListItem
                v-for="i in comments"
                :title="i.title"
                :comment="i.comment"
            />
        </ul>
    </div>
</template>

<style>

.centrer{
    text-align: center;
}

input, button{
    margin-top: 10px;
}

h1{
    margin: 20px 0px 0px 0px;
}



</style>

