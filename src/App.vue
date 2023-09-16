<script setup>
import {ref, watchEffect} from 'vue'

const alert = ref(false)
const alertMessage = ref('')

const textControlXpath = ref('')
const textControlCss = ref('')

const xpathValue = textControlXpath.value
const cssValue = textControlCss.value
alertMessage.value = 'OLUM DUR YAZIYOZ DAHA'

// watchEffect(() => {
//   // alertMessage.value = `${xpathValue} ≠ ${cssValue}`
// });
</script>

<template>
  <div class="card-title">
    <h1>Welcome to my Converter</h1>
  </div>
  <div class="container">
    <div class="col">
      <h4>Xpath Selector</h4>
      <textarea class="form-control" @keydown.enter.prevent v-model="textControlXpath" rows="5"></textarea>
    </div>

    <div class="col">
      <h4>Css Selector</h4>
      <textarea class="form-control" @keydown.enter.prevent rows="4" v-model="textControlCss"></textarea>
    </div>
  </div>

  <div class="alert">{{ alertMessage }}</div>
</template>

<style scoped>
.card-title h1 {
  font-size: 3rem;
  font-family: "PT Serif Caption";
  //font-weight: bold;
}
textarea {
  resize: none;
}

.alert {
  color: crimson;
}

.container {
  width: 100%;
  padding: 0 20rem;
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 2rem;
  flex-wrap: wrap;
}

.container .col {
  display: flex;
  flex-direction: column;
  justify-content: center;
  gap: 5px;
}
.container .col h4{
  font-size: 1.2rem;
  font-weight: bold;
  color: #f472b6;
}

.container .col .form-control {
  height: 7rem;
  min-width: 500px;
  width: 800px;
  box-sizing: border-box;
  padding: 10px 5px;
  border-radius: 10px;
  font-size: 1.1rem;
}

.container .col .form-control::placeholder {
  font-size: 1.2rem;
  color: #5ad52c;
}

.container .col .form-control::-webkit-scrollbar {
  width: 0;
}

</style>