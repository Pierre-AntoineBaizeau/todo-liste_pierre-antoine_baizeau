<template>
   
    <li><label class="checkbox">
            <input type="checkbox">
        </label>
      {{ title }}
      <button class="button is-light" v-on:click="$emit('remove')">Supprimer</button>
    </li>

    
</template>

<script>
export default {
    components: {

    },
    data() {
        
    },
    props: ['title']
}
</script>

<style>

li {
    list-style: none;
}

</style>