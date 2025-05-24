<script setup>
    import { computed } from 'vue';

    const props = defineProps(['books']);

    const booksRead = computed(() => {
        return props.books.filter(x => x.isRead).length;
    });

    const booksReadMessage = computed(() => {
        return booksRead.value >= props.books.length
                ? 'Congratulations, you read all the books!'
                : `${booksRead.value} out of ${props.books.length} books read`;
    });
</script>

<template>
    <div class="books-read">
        <label for="progress">Your progress</label><br>
        <progress :value="booksRead" :max="books.length"></progress>
        <p>{{ booksReadMessage }}</p>
    </div>
    
</template>