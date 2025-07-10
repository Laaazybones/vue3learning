<template>
  <div class="person">
    <h2>姓名：{{ name }}</h2>
    <h2>年龄：{{ age }}</h2>
    <button @click="changeName">展示姓名</button>
    <button @click="changeAge">展示年龄</button>
    <button @click="showTel">展示电话号码</button>
  </div>
</template>

<!-- <script lang="ts">
    export default {
        name: 'Person',
    }
</script> -->

<script lang="ts" setup name="Person">
    import { ref } from 'vue';

    let name = ref('张三');
    let age = ref(18);
    let tel = '13899990000'

    function changeName() {
        console.log('1')
        name.value = 'zhang-san'
        console.log(name.value)
    }

    function changeAge() {
        console.log('2')
        age.value += 1
        console.log(age.value)
    }

    function showTel() {
        alert(tel)
    }
</script>

<style scoped>
    .person {
        background-color: skyblue;
        box-shadow: 0 0 10px;
        border-radius: 10px;
        padding: 20px;
    }

    button {
        margin: 0 5px;
    }
</style>