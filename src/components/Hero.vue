<script setup>
 const {isThrones} = defineProps(['isThrones'])

 const emit = defineEmits(["selectShow"])

 const emitSelectShow = () => {
  emit("selectShow")
 }
</script>


<template>
  <div class="hero">
    <h1>{{ isThrones ? 'Thrones' : 'Rick and Morty' }}</h1>
    <p @click="emitSelectShow">{{ isThrones ? 'Rick and Morty' : 'Thrones' }}</p>

  </div>
</template>

<style scoped>
.hero {
    height : 40vh;
    display: flex;
    align-items: center;
    justify-content: center;
    position: relative;
    flex-direction: column
}
.hero img {
    position: absolute;
    height: 700px;
    opacity: 0.1;
}
.hero h1 {
    font-size: 100px;
    font-weight: bold;
}
.hero p {
    cursor: pointer;
}
</style>
