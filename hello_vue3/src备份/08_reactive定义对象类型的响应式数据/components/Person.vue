<template>
  <div class="person">
    <div>
        销售汽车：{{ car.name }}, 价格：{{ car.price }} 万元
    </div>
    <div>
        <button @click="changeCarPrice">修改汽车价格</button>
    </div>

    <div>游戏列表：</div>
    <ul>
        <li v-for="g in games" :key="g.id">
            {{ g.name }}
        </li>
    </ul>
    <div>
        <button @click="changeGameName">修改游戏名称</button>
    </div>
    <hr>
    <div>
        obj: {{ customObj.a.b.c }}
    </div>
    <div>
        <button @click="changeObj">修改obj的值</button>
    </div>
  </div>
</template>

<script lang="ts" setup name="Person">
    import { reactive } from 'vue';

    // 对象
    let car = reactive({ name:'Miyata MX-5', price: 30 });

    // 数组
    let games = reactive([{id:'dqhnjnoaidoa01', name:'诛仙世界'},
    {id:'dqhnjnoaidoa02', name:'英雄联盟'},
    {id:'dqhnjnoaidoa03', name:'喷射战士'}])

    let customObj = reactive({ 
        a:{
            b: {
                c: 666
            }
        } 
    })

    function changeCarPrice() {
        car.price -= 1
    }
    function changeGameName() {
        games[0].name = '塞尔达传说-荒野之息'
    }
    function changeObj() {
        customObj.a.b.c = 999;
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