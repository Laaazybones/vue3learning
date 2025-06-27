<template>
  <div class="person">
    <!-- <h2>姓名：{{ name }}</h2>
    <h2>年龄：{{ age }}</h2>
    <button @click="changeName">展示姓名</button>
    <button @click="changeAge">展示年龄</button>
    <button @click="showTel">展示电话号码</button> -->
  </div>
</template>

<script lang="ts">
    export default {
        name: 'Person',
        data() {
            return {
                name: "zhang-san",
                age: 19
            }
        },
        methods: {
            aFun() {
                console.log('aFun')
            }
        },
        setup() {
            // console.log(this)    setup函数中的this是undefined，Vue3中已经弱化了this
            // setup 中定义的属性是非响应式的
            let name = '张三'
            let age = 18
            let tel = '13899990000'

            // 这样可以修改属性值，但是不是响应式，不会直接在页面上展示
            function changeName() {
                console.log('1')
                name = 'zhang-san'
                console.log(name)
            }

            function changeAge() {
                console.log('2')
                age += 1
                console.log(age)
            }

            function showTel() {
                alert(tel)
            }

            // return { name, age, changeName, changeAge, showTel }
            // setup的返回值也可以是一个渲染函数
            return () => '哈哈'
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