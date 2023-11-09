<script setup>
import { ref } from 'vue';

const emit = defineEmits([ 'submitted' ]);

const title =ref('');
const comment =ref('');
    
    const onSubmitForm = () => {
        fetch('https://kommentar-7811a-default-rtdb.europe-west1.firebasedatabase.app//kommentar.json', {
            method: 'POST',
            body: JSON.stringify({
                title: title.value,
                comment: comment.value,

            })
        })
            .then((res) => {
                emit('submitted');
                resetForm;
            })
    };

    const resetForm = () => {
        title.value = '';
        comment.value = '';
    };
</script>


<template>
    <h1>Anmeldelse af besøg</h1>
    <form v-on:submit.prevent="onSubmitForm">
    <input type="text" v-model="title" placeholder="Titel"  /><br>
    <input type="text" v-model="comment" placeholder ="Kommentar" /><br>
    <button type="submit">Tilføj kommentar</button>
    </form>
</template>

