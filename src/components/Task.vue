<template>
<div :class="[task.reminder ? 'reminder' : '', 'task']">
    <h3>{{task.text}}
        <fa @click="onDelete(task.id)" icon="times" class="icon"/>
    </h3>
    <p>{{task.day}}</p>
</div>
</template>

<script>
export default {
    name: 'Task',
    props: {
        task: Object,
    },
    methods: {
        onDelete(id) {
            this.$emit('delete-task', id)
        }
    }
}
</script>

<style scoped>

    .icon {
    color: red;
    }

    .task {
    background: #f4f4f4;
    margin: 5px;
    padding: 10px 20px;
    cursor: pointer;
    }

    .task.reminder {
    border-left: 5px solid green;
    }

    .task h3 {
    display: flex;
    align-items: center;
    justify-content: space-between;
    }
</style>