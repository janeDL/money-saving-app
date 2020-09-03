<template>
  <div class="mt-16 mx-auto max-w-sm px-4">
    <div class="bg-white rounded-md shadow-md overflow-hidden">
      <!-- 上面的图片 -->
      <div>
        <img
          class="h-48 w-full object-cover object-top"
          src="./assets/ringfit.jpg"
          alt="健身环大冒险"
        />
      </div>
      <!-- 下面的div -->
      <div class="px-5 py-4">
        <div class="flex items-baseline justify-between">
          <div class="flex-none flex items-baseline">
            <span class="font-bold text-lg text-gray-600"> ¥ </span>
            <span class="ml-1 font-bold text-3xl text-gray-800">
              {{ currentSaving }}
            </span>
            <span class="ml-1 text-lg text-gray-600">/ {{ targetAmount }}</span>
            <span v-if="currentSaving === targetAmount">
              Hooray，目标已达成 🎉
            </span>
          </div>
          <div class="flex items-center">
            <button class="text-gray-600" @click="currentSaving -= add">
              -
            </button>
            <input
              v-model.number="add"
              class="h-6 w-8 border rounded mx-1 bg-gray-200 text-center text-gray-600"
            />
            <button class="text-gray-600" @click="currentSaving += add">
              +
            </button>
          </div>
        </div>
        <div class="mt-4 flex flex-wrap justify-around">
          <button
            v-for="v in values"
            :key="v"
            class="h-6 w-8 rounded-md leading-none text-sm font-bold bg-blue-100 text-blue-700"
            @click="add = v"
          >
            {{ v }}
          </button>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'App',
  data: () => ({
    targetAmount: 750,
    currentSaving: 80,
    add: '',
    values: [5, 10, 15, 20, 25, 50],
  }),
  // created () {
  //   fetch('')
  //   .then(this.targetNum=xxx)
  // },
  // computed: {
  //   newSaving () {
  //     return this.currentSaving.
  //   }
  // }
}
</script>
