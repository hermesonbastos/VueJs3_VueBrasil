<template>
  <div>
    <h1>Minha lista de tarefas</h1>
    <input type="text" v-focus>
    <br>
    <button @click="() => showList = !showList">Ver a lista</button>
    <ul v-if="showList">
      <li v-for="(task, index) in tasks" :key="`${task}-${index}`">
        {{ task.name }}
      </li>
    </ul>
    <p v-else>Lista de tarefas escondida</p>
  </div>
</template>

<script>
const focus = {
  mounted: (el) => {
    el.focus();
  }
}

export default {
  directives: {
    focus
  },
  data: () => ({
    showList: false,
    tasks: [
      { name: 'Fazer o curso', isDone: false },
      { name: 'Fazer o lanche', isDone: false },
      { name: 'Estudar', isDone: false },
    ]
  })
}
</script>

<style>

</style>