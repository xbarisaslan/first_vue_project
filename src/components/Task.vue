<template>
<div @dblclick="$emit('toggle-reminder' , task.id)" :class="[task.reminder ? 'reminder' : '', 'task']"> <!--If task.reminder is true add a class of 'reminder' else don't do anything.The 'task' class is always there.-->
    <h3>
        {{task.text}}
        <i @click="$emit('delete-task' , task.id)" class="fas fa-times"></i>
    </h3>
    <p>{{task.day}}</p>
</div>
</template>

<script>
export default {
    name: "Task",
    props: {
        task: Object,
    },
    }

</script>

<style>
 .task {
    background-color: #f4f4f4;
    margin: 5px;
    padding: 10px 20px;
    cursor: pointer;
 }

 .task.reminder {
    border-left: 5px solid rgba(21, 193, 98, 0.8);
 }

.task h3 {
    display:flex;
    align-items: center;
    justify-content: space-between;
}

.fas {
    color: rgba(233, 0, 80, 1)
}
</style>




