<teamplate>
    <li>
        <div>{{ task.name }} {{ index }}</div>
        <small>{{ task.duaDate }} @ {{ task.dueTime }}</small>
        <button @click="deleteTask(index)">X</button>
    </li>
</teamplate>

<script>

</script>
