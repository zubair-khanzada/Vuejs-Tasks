<template>
  <div class="home">
    <v-btn color="primary" icon="mdi-plus" size="small" @click="increaseNumber"></v-btn>
    <span>{{ count }}</span>
    <v-btn color="primary" icon="mdi-minus" size="small" @click="decreaseNumber"></v-btn>
  </div>
</template>

<script>

export default {
  data () {
    return {
      count: 0,
    }
  },
  methods: {
    increaseNumber() {
      this.count++
    },
    decreaseNumber() {
      if (this.count > 0) {
        this.count--
      }
    }
  }
}
</script>

<style>

.home {
  gap: 20px;
  display: flex;
  padding: 15px 10px;
  align-items: center;
  justify-content: center;
}

</style>
