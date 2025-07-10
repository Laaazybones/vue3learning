<template>
  <div class="person">
    <div>
        销售汽车：{{ car.name }}, 价格：{{ car.price }} 万元
    </div>
    <button @click="changeCarPrice">修改汽车价格</button>
    <button @click="changeCar">修改汽车</button>
    <hr>
    <div>sum: {{ sum }}</div>
    <button @click="sumAdd">sum+1</button>
  </div>
</template>

<!-- 对于reactive定义的响应式对象，要整体修改对象时，只能使用 Object.assign() 方法 -->
<script lang="ts" setup name="Person">
    import { ref,reactive } from 'vue';

    // 对象
    let car = reactive({ name:'Miyata MX-5', price: 30 });

    let sum = ref(0);

    function changeCarPrice() {
        car.price -= 1
    } 
    function sumAdd() {
        sum.value += 1
    }
    function changeCar() {
        // car = { name: 'BMW X5', price: 50 }; // 无效
        // car = reactive({ name: 'BMW X5', price: 50 })    // 无效
        Object.assign(car, { name: 'BMW X5', price: 50 })
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