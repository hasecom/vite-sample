<template>
<div>
    {{message}}
    <div>
        <ProviderGreatgrandchild />
    </div>
</div>
</template>

<script>
import ProviderGreatgrandchild from './providerGreatgrandchild.vue'
export default {
    components:{ProviderGreatgrandchild},
    inject: ['ProviderGrandchild','ProviderReactive'],
    created() {
        console.log(this.ProviderGrandchild);
        console.log(this.ProviderReactive)
    },
    computed:{
        message(){
            return this.ProviderReactive.reactiveStr
        }
    }
}
</script>
