<template>
    <center>
    <div class="calculator">
        <CalculatorScreen :screenValue="output"/>
        <CalcalutorInputGrid :ClickButton="ClickButton"/>
    </div>
    </center>
</template>

<script lang="ts">
import CalculatorScreen from '@/components/CalculatorScreen.vue'
import CalcalutorInputGrid from '@/components/CalulatorInputGrid.vue'
import Vue from 'vue'
import {Component} from 'vue-property-decorator';

@Component({
    name:'Calculator',
    components:{
        CalcalutorInputGrid,
        CalculatorScreen
    }
})
export default class Calculator extends Vue {
    num1=0
    num2=0
    operator: any =undefined
    output = 0
    ClickButton (data: string) {
         const operators= "+÷-*="
         if(operators.includes(data)) { 
            // Operator
            if(data == "=") {
                // Time to calculate
                switch (this.operator) {
                    case "+":
                        this.output = this.num1 + this.num2;
                        break;
                    case "-":
                        this.output = this.num1 - this.num2;
                        break;
                    case "÷":
                        this.output = this.num1 / this.num2;
                        break;
                    case "*":
                        this.output = this.num1 * this.num2;
                        break;
                    default:
                        break;
                    }
                console.log(this.output)
                this.num1=0
                this.num2=0
                this.operator=undefined
                }else {
                    // Add operator 
                    this.operator = data
                }
         }else {
            // Number comes here
            if(operators.includes(this.operator)) {
                // There is an operator add value to num2
                this.num2 = parseInt(data)
                this.output = this.num2
            }else {
                this.num1 = parseInt(data)
                this.output = this.num1
            }
         }
     }
}
</script>

<style scoped>
.calculator {
    max-width: 300px;
    background-color: grey;
    min-height: 400px;
    display: flex;
    flex-direction: column;
    position:relative;
}

</style>