<!-- eslint-disable vue/multi-word-component-names -->
<template>
  <div class="checkStep4 w-full h-screen fixed top-0 left-0">
    <div class="absolute left-1/2 top-1/2 -translate-x-1/2 -translate-y-1/2 z-50 w-full">
      <div class="flex justify-center mb-10 text-white w-full container mx-auto">
        <div class="">
          <div class="mb-8"><img src="@/assets/img/role1.png" class="object-contain -scale-x-100 mx-auto" /></div>

          <div v-show="result === 0">
            <p class="text-4xl mb-8">咦～你好像還沒完成唷！</p>
          <a @click="closeCheckStep4()" class="cursor-pointer btn-base text-4xl inline-flex justify-center items-center">
            <p class="z-10">返回挑戰</p>
          </a>
          </div>
          <div v-show="result === 1">
            <p class="text-4xl mb-8 leading-loose">你做得非常好！<br/>
                你已經能掌握基礎產品代辦清單的優先度排序<br/>
                接下來再繼續挑戰吧！</p>
            <a @click="nextStep()" class="cursor-pointer btn-base text-4xl inline-flex justify-center items-center">
              <p class="z-10">前往下個挑戰</p>
            </a>
          </div>
          <div v-show="result === 2">
            <p class="text-4xl mb-8">順序可以再調整看看唷！</p>
            <a @click="closeCheckStep4()" class="cursor-pointer btn-base text-4xl inline-flex justify-center items-center">
              <p class="z-10">再試試看</p>
            </a>
          </div>
        </div>
      </div>
    </div>
  </div>

</template>

<script>
export default {
  components: {
  },
  props: ['result'],
  setup (props, ctx) {
    const closeCheckStep4 = () => {
      ctx.emit('closeModule')
    }

    const nextStep = () => {
      ctx.emit('nextStep')
    }

    return {
      closeCheckStep4,
      nextStep
    }
  }
}
</script>
<style lang="scss" scoped>
.checkStep4 {
  background: rgb(24, 30, 42, 0.8);
  z-index: 9999;
}
</style>