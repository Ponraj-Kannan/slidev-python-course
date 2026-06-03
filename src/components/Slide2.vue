<template>
  <div class="slide-wrapper">
    <div class="navbar">
      <h2 class="navbar-title">{{ topic }}</h2>
      <img src="../assets/logo.png" />
    </div>
    <div class="slide-body">
      <slot name="content" /> <!-- html code here-->
    </div>
  </div>
</template>

<script setup>
defineProps({
  topic: {
    type: String,
    required: true,
  },
  subTopic: {
    type: String,
    default: '',
  }
});
</script>

<style scoped>
@import '../style.css';

.slide-wrapper {
  margin-top: -10px;
  margin-left: -30px;
  width: 107%;
  height: 65vh;
  font-size: 0.8rem;
  font-weight: 400;
  overflow-x: auto;
  overflow-y: auto;
  scrollbar-width: none;
  padding-bottom: 100px;
}
.slide-body {
  display: flex;
  flex-direction: column;
  border-radius: 4px;
  margin-top:50px;
}

.navbar {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  align-items: center;
  gap: 0.75rem;
  padding: 0 10px;
  color: #ffffff;
  position: fixed;
  width: 94.7%;
}

.navbar > img {
  height: 30px;
}

.navbar-title {
  margin: 0;
  font-size: 1.5rem;
  font-weight: 700;
  background-color: #ef5050;
  color: #ffffff;
  width: 80%;
  padding-left: 10px;
  margin-left: -10px;
  border-radius: 5px;
}
</style>