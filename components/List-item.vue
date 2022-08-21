<template>
  <div class="wrapper">
    <div
      :class="{ active: isActive }"
      @click="toggle"
    >
      <a class="title">
        <slot name="title" />
      </a>

      <div v-show="show" :class="{ active: isActive }" class="content">
        <slot name="content" />
      </div>
    </div>
  </div>
</template>

<script>
export default {
  components: {},
  data () {
    return {
      isActive: false,
      show: true
    }
  },
  methods: {
    myFiler () {

    },
    toggle () {
      // this.show = !this.show
      console.log('ping')
      this.isActive = !this.isActive
    }
  }
}

</script>

<style>

</style>
