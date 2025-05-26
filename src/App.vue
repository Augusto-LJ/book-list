<script setup>
  import {reactive, ref} from 'vue';
  import AddBook from './components/AddBook.vue';
  import Books from './components/Books.vue';
  import BookProgress from './components/BookProgress.vue';
  
  let books = reactive([
        {
          id: 1,
          title: "A psicologia financeira",
          cover:
            "https://m.media-amazon.com/images/I/81ehvI03NYS._SY466_.jpg",
          isRead: true,
          isbn: "9786555111101",
          author: "Morgan Housel",
        },
        {
          id: 2,
          title: "O homem mais rico da Babilônia",
          cover:
            "https://m.media-amazon.com/images/I/81ehX6Quw2L._SY466_.jpg",
          isRead: false,
          isbn: "9786555111583",
          author: "George S Clason",
        },
        {
          id: 3,
          title: "Pai Rico, pai Pobre",
          cover:
            "https://m.media-amazon.com/images/I/71V4lNR2gKL._SY425_.jpg",
          isRead: false,
          isbn: "9788535253191",
          author: " Robert T Kiyosaki",
        },
        {
          id: 4,
          title: "O investidor de bom senso",
          cover:
            "https://m.media-amazon.com/images/I/71f6pivF9aL._SY466_.jpg",
          isRead: false,
          isbn: "9788543110110",
          author: "John C. Bogle",
        },
      ]);

  function addBook (newbook) {
    newbook.id = Math.max(...books.map(x => x.id)) + 1;
    books.push(newbook);
    showAddBook.value = false;
  };
    
  let showAddBook = ref(false);
  
  function toggleIsRead (id) {
    books.forEach((book) => {
      if (book.id === id)
        book.isRead = !book.isRead;
      }
    )
  }
</script>

<template>
  <div>

    <div v-show="!showAddBook" class="container">
    <h1>📖 My books</h1>
    <div class="header-btns">
      <button
        class="btn"
        @click="showAddBook = true">
        Add book +
      </button>
    </div>
 
    <div class="books-container">
      <Books @toggleIsRead="toggleIsRead" :books="books" />
      <BookProgress :books="books" ></BookProgress>
    </div>
    </div>
    <div v-show="showAddBook" class="container">
      <AddBook @addBook="addBook" @closeAddBook="showAddBook = false"/>
    </div>

  </div>
</template>

<style scoped>

</style>
