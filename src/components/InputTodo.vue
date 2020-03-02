<template>
    <div>
        <form v-on:submit="onSubmit">

        <input type="text" v-model="todoinput" />
        </form>
    </div>
</template>

<script lang="ts">
import {Vue,Component,Prop} from 'vue-property-decorator'
@Component
export default class InputTodo extends Vue{
    todoinput = "";
    @Prop({})
    AddTodo: Function;


    onSubmit (event) {
        this.AddTodo(this.todoinput);
        event.preventDefault();
        this.todoinput= "";

    }

    // @Watch('todoinput')
    // onPropertyChanged(value: string,oldValue: string) {
    //     console.log(value)
    // }
}
</script>