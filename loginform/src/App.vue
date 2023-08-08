<script setup>
import {  ref } from 'vue';
import Login from './components/Login.vue'
import Registration from './components/Registration.vue'


const isRegistered=ref(false)
const buttonText=ref('Login')
function changeComponent(){
  isRegistered.value=!isRegistered.value
  buttonText.value=isRegistered.value==true?'Register':'Login'
  
}
</script>
<template>
  <div>
    <Login v-show="isRegistered"/>
    <Registration v-show="!isRegistered" />
  </div>
  <div>
          <button @click="changeComponent()" type="submit" class="flex w-full justify-center rounded-md bg-indigo-600 px-3 py-1.5 text-sm font-semibold leading-6 text-white shadow-sm hover:bg-indigo-500 focus-visible:outline focus-visible:outline-2 focus-visible:outline-offset-2 focus-visible:outline-indigo-600">
            {{buttonText}}
          </button>
  </div>
 
</template>

<style scoped>

</style>
