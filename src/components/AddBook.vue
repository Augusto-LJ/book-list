<script setup>
    const emit = defineEmits(['addBook', 'closeAddBook']);
    let newBook = {
          title: "",
          cover: "",
          isRead: false,
          isbn: "",
          author: "",
        }
</script>

<template>
    <h1>📖 Add book</h1>
    
    <div class="header-btns">
      <button class="btn" @click="$emit('closeAddBook')">
        Close x
      </button>
    </div>
 
    <form class="add-form">
       
        <div class="form-control">
        <label>Title</label>
        <input
            type="text"
            name="text"
            placeholder="Add the title"
            v-model="newBook.title"
            required
        />
        </div>
        <div class="form-control">
        <label>Cover link</label>
        <input 
            type="text" 
            name="cover" 
            placeholder="Add the link for the cover"
            v-model="newBook.cover"
            required
            />
        </div>
        <div class="form-control">
        <label>Author</label>
        <input
            type="text"
            name="author"
            placeholder="Add the author"
            v-model="newBook.author"
        />
        </div>
        <div class="form-control">
        <label>ISBN#</label>
        <input 
            type="text" 
            name="isbn" 
            placeholder="Add ISBN"
            v-model="newBook.isbn"
        />
        </div>
        <div class="form-control form-control-check">
        <input 
            type="checkbox" 
            name="readIt" 
            id="readIt"
            v-model="newBook.isRead"
            />
        <label for="readIt">Read it</label>
        </div>
 
        <button @click.prevent="$emit('addBook', newBook)" type="submit" class="btn btn-block">Save book</button>
    </form>
</template>