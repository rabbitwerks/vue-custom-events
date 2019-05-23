<template>
  <div class="parent--outer" :style="{ 'background-color': receivedDataColor }">
    <h1>Parent Component</h1>
    <div class="parent--inner">
      <ChildComponent @sending-color-data="receivedColor"/>

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
      this.receivedDataColor = payload;
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
  justify-content: center;
}

</style>

