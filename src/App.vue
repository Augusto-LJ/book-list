<script setup>
  import Books from './components/Books.vue';
  
  let books = [
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
      ]
</script>

<template>
  <div>

    <div class="container">
    <h1>📖 My books</h1>
    <div class="header-btns">
      <button
        class="btn">
        Add book +
      </button>
    </div>
 
    <div class="books-container">
      <Books :books="books" />
    </div>
  </div>

  </div>
</template>

<style scoped>

</style>
