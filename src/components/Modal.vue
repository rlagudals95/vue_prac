
<template>
  <!-- props로 받은 함수는 이렇게 써야한다 -->
  <div class="black-bg" @click="$emit('closeModal')">
    <div class="white-bg">
      <h4>상세페이지</h4>
      <p>상세페이지 내용</p>
      <img :src="modalProps.image" />
      <div>{{ modalProps }}</div>
    </div>
  </div>
</template>

<script>
export default {
  name: "modal",
  data() {
    return {};
  },
  methods: {},
  props: {
    modalProps: Object,
    closeModal: Function,
    // props 타입을 설정안해줘도 오류는 안뜬다...
  },
};
</script>

<style >
div {
  box-sizing: border-box;
}

.black-bg {
  width: 100%;
  height: 100%;
  background-color: rgba(0, 0, 0, 0.7);
  position: fixed;
  top: 0;
}

.white-bg {
  margin: 0 auto;
  width: 90%;
  height: 80%;
  background-color: white;
  border-radius: 8px;
  padding: 20px;
  position: fixed;
  left: 50%;
  top: 50%;
  transform: translate(-50%, -50%);
}
.menu {
  background: darkslateblue;
  padding: 15px;
  border-radius: 5px;
  display: flex;
  justify-content: space-evenly;
}

.menu a {
  color: white;
  padding: 10px;
}
.btn {
  margin-right: 1rem;
}

.image {
  width: 100%;
  background-size: cover;
}
</style>