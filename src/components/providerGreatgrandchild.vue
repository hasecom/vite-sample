<template>
<div>
    <div>{{message}}</div>
    <div>{{sampleText}}</div>
</div>
</template>

<script>
export default {
    inject: ['ProviderGrandchild', 'ProviderReactive'],
    data(){
        return{
            sampleText:this.ProviderGrandchild
        }
    },
    mounted() {
        setTimeout(() => {
            this.sampleText = "sample!";
        }, 1000);
    },
    computed: {
        message() {
            return this.ProviderReactive.reactiveStr;
        },
        message2(){
            return this.sampleText;
        }
    }
}
</script>
