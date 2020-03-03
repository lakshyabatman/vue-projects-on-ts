<template>
    <div class="inputs">
            <CalculatorInput :ClickButton="ClickButton">9</CalculatorInput>
            <CalculatorInput :ClickButton="ClickButton">8</CalculatorInput>
            <CalculatorInput :ClickButton="ClickButton">7</CalculatorInput>
            <CalculatorInput :isOperator="true" :ClickButton="ClickButton">+</CalculatorInput>
            <CalculatorInput :ClickButton="ClickButton">6</CalculatorInput>
            <CalculatorInput :ClickButton="ClickButton">5</CalculatorInput>
            <CalculatorInput :ClickButton="ClickButton">4</CalculatorInput>
            <CalculatorInput :isOperator="true" :ClickButton="ClickButton">÷</CalculatorInput>
            <CalculatorInput :ClickButton="ClickButton">3</CalculatorInput>
            <CalculatorInput :ClickButton="ClickButton">2</CalculatorInput>
            <CalculatorInput :ClickButton="ClickButton">1</CalculatorInput>
            <CalculatorInput :isOperator="true" :ClickButton="ClickButton">-</CalculatorInput>
            <CalculatorInput :ClickButton="ClickButton" :isBig="true">0</CalculatorInput>
            <CalculatorInput :isOperator="true" :ClickButton="ClickButton">=</CalculatorInput>
    </div>
</template>

<script lang="ts">
import CalculatorInput from './CalculatorInput.vue'
import Vue from 'vue';
import {Component,Prop} from 'vue-property-decorator';

@Component({
    name:'CalculatorInputGrid',
    components: {
        CalculatorInput
    }
})
export default class CalculatorInputGrid extends Vue {

    @Prop({})
    ClickButton: Function| undefined;

}

</script>

<style scoped>
.inputs {
    min-height: 340px;
    background-color: rgb(41, 148, 41);
    display: grid;
    grid-template-columns: auto auto auto auto;
}
</style>>

