<template>
  <img class="image" :src="info.image" @click="modalOpen = true" />
  <h3>{{ info.title }}</h3>
  <p>{{ info.price }}만원</p>
  <p>{{ info.content }}</p>
  <modal v-if="modalOpen" :modalProps="info" @closeModal="modalOpen = false" />
</template>
<script>
import modal from "./Modal.vue";
export default {
  name: "oneRoom",
  data() {
    return {
      modalOpen: false,
    };
  },
  props: {
    info: Object,
  },
  methods: {},
  components: { modal },
};
</script>