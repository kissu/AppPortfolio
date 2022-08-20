<template>
  <div class="wrapper">
    <div
      :class="{ active: isActive }"
      @click="toggle"
    >
      <h2 class="title">
        <slot name="title" />
      </h2>

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
      this.isActive = !this.isActive
    }
  }
}

</script>

<style>

</style>
