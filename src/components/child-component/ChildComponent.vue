<template>
  <div class="child--outer">
    <h2>Child Component</h2>

    <div class="child--inner">
      <h3>Select Color</h3>
      <input type="color" v-model="colorData">
      <button @click="sendColorData">Send Color To Parent</button>
      <h4>Selected Color: {{ colorData }}</h4>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      colorData: '#a2d113',
    }
  },
  methods: {
    sendColorData() {
      const payload = {
        origin: {
          vueInstance: this.$options._componentTag,
          domElement: this.$el,
        },
        data: this.colorData,
      }
      this.$emit('sending-color-data', payload)
    }
  }
}
</script>

<style>
.child--outer {
  width: 33%;
  border: 2px solid rgb(4, 59, 41);
  min-height: 20rem;
  background-color: #f1f1f1;
  padding: 0 4rem;
}
.child--inner {
  height: 60%;
  display: flex;
  flex-direction: column;
  align-items: center;
}
input {
  width: 50%;
  background-color: #a4ebd0;
  border: 2px solid #10524c;
  padding: .25rem 1rem;
  margin-bottom: 1.5rem;
}
button {
  width: 59.5%;
  background-color: #a4ebd0;
  border: 2px solid #10524c;
  padding: .5rem 1rem;
}

@media screen and (max-width: 480px) {
  .child--outer {
    width: 90%;
  }
}
</style>
