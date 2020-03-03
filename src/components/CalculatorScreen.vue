<template>
    <div class="screen"><span class="num">{{screenValue}}</span></div>
</template>

<script lang="ts">
import Vue from 'vue'
import {Component,Prop} from 'vue-property-decorator';

@Component({
    name:'CalculatorScreen'
})
export default class CalculatorScreen extends Vue {
    @Prop({default:0})
    screenValue: string | number;

}
</script>

<style scoped>
.num {
    position: absolute;
    right:6px;
    top:10px;
    font-size: 30px;
    color:white;
}
.screen {
    min-height: 60px;
    background-color:black;
    border: 5px solid green;
}
</style>