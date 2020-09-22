<template>
    <form v-on:submit.prevent="bookSubmit(bookTitle,bookAuthor)" class="" action="#" method="post">
        <input type="text" name="title" value="" v-model="bookTitle" placeholder="Book Title">
        <input type="text" name="author" value="" v-model="bookAuthor" placeholder="Book Author">
        <button type="submit" name="button">Add Book</button>
    </form>
</template>
<script>
export default {
    name: 'BookForm',
    props: ['books'],
    data() {
        return {
            bookTitle: '',
            bookAuthor: '',
        };
     },
  methods: {
    bookSubmit(bookTitle,bookAuthor) {
      this.$emit('addBook', bookTitle, bookAuthor);
    },
  },
}
</script>
<style scoped>

</style>