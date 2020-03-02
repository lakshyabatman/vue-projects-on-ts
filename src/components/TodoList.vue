<template>
    <div>
        <ul class="Todos">
            <li v-for="(todo,index) in todos" v-bind:key="index">{{todo}}</li>
        </ul>
    </div>
</template>

<script lang="ts">
import Vue from 'vue'
import {Component,Prop} from 'vue-property-decorator'

@Component
export default class TodoList extends Vue {
    @Prop({default:()=> []})
    todos: Array<string>;
}
</script>
<style scoped>
.Todos {
  list-style:none;
  color:white;
  margin: 0;
  margin-top: 10px;
  padding: 0;
  display: flex;
  align-items: center;
  width:100%;
  flex-direction: column;
}
.Todos > li {
    width:300px;
    background-color:cadetblue;
    padding: 10px;
    margin-top:10px;
}
</style>