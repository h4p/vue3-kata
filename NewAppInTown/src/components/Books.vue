<template>
  <h1>{{ author }}</h1>
  <div id="computed-basics">
    <p>Has published books:</p>
    <span>{{ book_list.books.length > 0 ? 'Yes' : 'No' }}</span>
  </div>
</template>

<script lang="ts">
import { ref, defineComponent } from 'vue'
export default defineComponent({
    name: 'Books',
    props: {
        author: {
            type: String,
            required: true
        }
    },
    data() {
        return {
            book_list: {
                name: 'John Doe',
                books: [
                'Vue 2 - Advanced Guide',
                'Vue 3 - Basic Guide',
                'Vue 4 - The Mystery'
                ]
            }
        }
    },
    created() {
        console.log("Book component was created!");
    },
    setup: () => {
        const count = ref(0)
        return { count }
    }
})
</script>

<style scoped>
#computed-basics {
  background-color: aliceblue;
}

a {
  color: #42b983;
}
</style>