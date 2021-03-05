
<template>

    <div class="field has-addons">
        <div class="control" id="send">
            <input v-model="newTaskText" id="new-todo" class="input" placeholder="Nouvelle tâche...">
        </div>

        <div class="control" id="components">
            <button  class="button is-info" v-on:click="sendTask">+</button>
        </div>
    </div>

</template>

<script>

export default {
    data() {
        // return {
        //     task : "",
        // };
    },
    methods: {
        // sendTask() {
        //     this.$emit("newTask", this.task);
        // }

         addTask: function () {
            this.tasks.push.$emit('ajoutertask',{
            id: this.nextTaskId++,
            title: this.newTaskText
      })
      this.newTaskText = ''
    }
    }
}
</script>

<style>

</style>