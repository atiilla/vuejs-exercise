<script>
import { useCounterStore } from '../stores/counter'
import { defineComponent } from 'vue';

export default defineComponent({
  name: 'HomeView',
  setup() {
    const CounterStore = useCounterStore();
    const hello = "hello world"
    const names = ['joe', 'bob', 'jane']
    return { CounterStore, hello, names };
  },
  data(){
    return {
      posts: []
    }
  },
  methods: {
    Increase() {
      this.CounterStore.increment();
      console.log('hello', this.CounterStore.count)
    }
  },
  mounted() {
    console.log('hello mounted')
    fetch('https://jsonplaceholder.typicode.com/users')
      .then(response => response.json())
      .then(json => {
        this.posts = json
        console.log(this.posts)
      })
  }
})

</script>

<template>
  <main>
    <h1>hello</h1>
    <button @click="Increase">increment</button>
    <p>count: {{ CounterStore.count }}</p>
    <h1>{{ hello }}</h1>
    <ul>
      <li v-for="username in names" :key="username">
        {{ username }}
      </li>
    </ul>
    <ul>
    <li v-for="post in posts" :key="post.id">
      {{ post.name }}
    </li>
      </ul>
  </main>
</template>
