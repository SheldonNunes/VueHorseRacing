<template>
    <div class="horse">
        <h2>{{number}}</h2>
        <h2>{{name}}</h2>
        <p>Jockey: {{jockey}}</p>
    </div>
</template>


<script>
export default {
  name: 'Horse',
  props: ['name','jockey','number'],
}
</script>

<style scoped>
.horse {
    background-color: #f5f4f4;
    display: inline-block;
    width: 20%;
    padding: 30px;
    margin: 20px;
}
h2 {
  color: red;
}
</style>