<template>
<div class="main-menu">
  <div class="section">
    <div class="bg-white p-8 rounded-3xl">
      <div class="flex flex-wrap mb-2 pt-4">
        <div class="w-full px-3 mb-6 md:mb-0">
          <label class="block tracking-wide text-black text-xs font-bold mb-2" for="grid-city">
            From
          </label>
          <input v-model="from" @change="cek($event)"  class="appearance-none block w-full text-black border border-gray-200 rounded py-3 px-4 leading-tight focus:outline-none focus:bg-white focus:border-gray-500" id="grid-city" type="text">
        </div>
      </div>
      <div class="flex flex-wrap mb-2 pt-4">
        <div class="w-full px-3 mb-6 md:mb-0">
          <label class="block tracking-wide text-black text-xs font-bold mb-2" for="grid-city">
            To
          </label>
          <input v-model="to" @change="cek($event)"  class="appearance-none block w-full text-black border border-gray-200 rounded py-3 px-4 leading-tight focus:outline-none focus:bg-white focus:border-gray-500" id="grid-city" type="email">
        </div>
      </div>
      <button class="cek-biaya focus:outline-none justify-end text-white font-bold py-2 px-4 rounded-full">
        Cek biaya
      </button>
    </div>
  </div>
</div>
</template>
<script>
import { ref } from '@nuxtjs/composition-api'
import axios from 'axios'
export default {
  name: 'Mailgun',
  components: {
  },
  setup(){
    const from = ref('Admin')
    const to = ref('ngodingbentat.official@gmail.com')

    return {
      from,
      to,
      cek,
    }
    
    function cek() {
      console.log('biayaJne',from.value)
      console.log('biayaPos',to.value)
    }
  }
}
</script>

<style lang="postcss" scoped>
.main-menu{
  background: rgb(241, 241, 241);
  @apply min-h-screen pb-16 pt-16 flex justify-center ;
}
.section {
  @apply mb-8 px-8 w-full;
  max-width: 700px;
}
.section-input {
  @apply w-full p-8;
}
.main {
  @apply flex;
}

.cek-biaya {
  background: #0fbcf9;
}

@media only screen and (max-width: 650px) {
  .main {
    @apply block;
  }
  .section {
    @apply px-2 pt-4;
  }
  .section-input {
    @apply w-full p-2;
  }
  .content {
    @apply w-full border-r-0 border-l-0;
  }
}

</style>