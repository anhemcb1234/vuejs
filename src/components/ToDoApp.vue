<template>
  <div class="container">
      <input  type="text" v-on:change="changeHandler" placeholder="Nhập việc bạn muốn làm " v-model="name">  
      <h1 class="m-4">Danh sách việc làm</h1>
      <ul>
            <li v-for="item, index in toDo" :key="item.message">
                {{index}}. {{ item.job }}<button class="m-3" @click="handleDel(index)">Xoa</button> <input v-show="active" type="text" v-on:change="e => updateChange(index, e)"> <button class="m-3" @click="active = !active">Sua</button>
            </li>
      </ul>
  </div>
</template>

<script>
import uniqid from 'uniqid';
export default {
    name: 'HelloWorld',
    data(){
        return {
            toDo: [],
            active: false
        }
    },
    methods: {
        changeHandler(e) {
            this.toDo.push({
                job:e.target.value,
                id: uniqid()
            })
        },
        handleDel(index) {
            return this.toDo.splice(index, 1)
        },
        updateChange(index, e) {
            return this.toDo[index].job = e.target.value
        }
    },
}
</script>

<style>
    .hide {
        display: none;
    }
    ul li {
        list-style: none;
    }
    input {
        border-radius: 10px;
        padding: 5px 20px;
    }
    button {
        padding: 10px;
        border: none;
        border-radius: 10px;
    }
    button:hover {
        background: #000;
        color: #fff;
    }
</style>