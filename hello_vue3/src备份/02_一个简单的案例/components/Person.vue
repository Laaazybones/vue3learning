<template>
  <div class="person">
    <h2>姓名：{{ name }}</h2>
    <h2>年龄：{{ age }}</h2>
    <button @click="changeName">展示姓名</button>
    <button @click="changeAge">展示年龄</button>
    <button @click="showTel">展示电话号码</button>
  </div>
</template>

<script lang="ts">
    export default {
        name: 'Person',
        data() {
            return {
                name: '张三',
                age: 18,
                tel: '18787878899'
            }
        },
        methods: {
            showTel() {
                alert(this.tel)
            },
            changeName() {
                this.name = 'zhang-san'
            },  
            changeAge() {
                this.age += 1
            }
        }
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