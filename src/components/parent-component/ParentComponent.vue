<template>
  <div class="parent--outer" :style="{ 'background-color': receivedDataColor }">
    <h1>Parent Component</h1>
    <div class="parent--inner">
      <h4>Received Color: {{ receivedDataColor || 'natta' }}</h4>
      <ChildComponent @sending-color-data="receivedColor" @click="console.log('click')" />
    </div>
  </div>
</template>

<script>
import ChildComponent from '../child-component/ChildComponent';

export default {
  name: 'ParentComponent',
  data() {
    return {
      receivedDataColor: ''
    }
  },
  components: {
    ChildComponent
  },
  methods: {
    receivedColor(payload) {
      this.receivedDataColor = payload.data;
      console.log('emitted from: ', payload.origin);
      console.log('listened on: ', { vueInstance: this.$options._componentTag, domElement: this.$el});
    }
  }
}
</script>

<style>
.parent--outer {
  width: 60%;
  min-height: 40vh;
  padding-bottom: 3rem;
  border: 3px solid rgb(16, 38, 44);
}
.parent--inner {
  display: flex;
  flex-direction: column;
  align-items: center;
}
@media screen and (max-width: 480px) {
  .parent--outer {
    width: 95%;
  }
}
</style>

