<template>
  <div>
    <button @click="fetchData">백엔드 호출7</button>
    <div v-if="showResponse">
      <!-- 백엔드에서 받은 데이터 표시 -->
      <p>{{ responseData }}</p>
    </div>
    <div v-if="error">
      <!-- 에러 메시지 표시 -->
      <p>{{ error }}</p>
    </div>
  </div>
</template>

<script>

import axios from 'axios';

export default {
  name: 'HelloMessage',
  data() {
    return {
      responseData: null,
      error: null,
      showResponse: true // 초기에는 true로 설정
    };
  },
  methods: {
    async fetchData() {
      try {
        const response = await axios.get('http://localhost:8080/user/create');
        this.responseData = response.data;
        this.error = null; // 이전에 발생한 에러를 초기화
      } catch (error) {
        this.responseData = null; // 오류가 발생했을 때 응답 데이터 초기화
        this.error = error.message; // 에러 메시지 설정
      }
    }
  }
}
</script>

<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
