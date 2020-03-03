<template>
    <div :class="calcClasses" @click="Click">
        <slot/>
    </div>
</template>

<script lang="ts">
import Vue from 'vue'
import {Component,Prop} from 'vue-property-decorator';
@Component({
    name:'CalculatorInput'
})
export default class CalculatorInput extends Vue {
    @Prop({})
    ClickButton: Function | undefined;

    @Prop({default:false})
    isOperator: boolean

    @Prop({default:false})
    isBig: boolean

    Click(event: object) {
        this.ClickButton(event.target.innerHTML)
    }

    get calcClasses() {
        let outputClass = "input-num"
        if(this.isOperator) {
            outputClass+= " operator"
        }
        if(this.isBig) {
            outputClass+=" big"
        }
        return outputClass
    }
}
</script>
<style scoped>

.operator {
    background-color: wheat;
}
.input-num {
    display: flex;
    justify-content: center;
    align-items: center;
    cursor: pointer;
    border-bottom: 1px solid black;
}
.big {
    grid-area: 4/1/4/4;
}
.input-num:active {
    background-color:rgb(29, 112, 29);
}

</style>