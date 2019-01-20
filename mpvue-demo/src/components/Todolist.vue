<template>
  <div class="todolist">
    <input type="text" v-model="mytodo" @keyup.enter="handleClick" />
    <button @click="handleClick">添加</button>
    <button @click="clean">清空</button>
    <ul>
      <li
        v-for="(todo, idx) in todos"
        :key="idx"
        :class="{
          'done': todo.done
        }"
        @click="toggle(idx)"
      >{{idx}} {{todo.text}}</li>
    </ul>
    <p>{{remains}}/{{todos.length}}</p>
  </div>
</template>

<script>
export default {
  name: 'Todolist',
  data () {
    return {
      todos: [
        {text: '吃饭', done: false},
        {text: '睡觉', done: false},
        {text: '写代码', done: false}
      ],
      mytodo: ''
    }
  },
  computed: {
    remains () {
      return this.todos.filter(v => !v.done).length
    }
  },
  methods: {
    handleClick () {
      this.todos.push({
        text: this.mytodo,
        done: false
      })
      this.mytodo = ''
    },
    toggle (i) {
      this.todos[i].done = !this.todos[i].done
    },
    clean () {
      this.todos = this.todos.filter(v => !v.done)
    }
  }
}
</script>

<style scoped>
li.done {
  text-decoration: line-through;
  color: red;
}
</style>
