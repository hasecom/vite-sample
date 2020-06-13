<template>
<div>
    <div>
        <provider-sample />
    </div>
    <div>
        <errorHandler />
    </div>
</div>
</template>

<script>
import providerSample from './components/providerSample.vue'

export default {
    name: 'App',
    components: {
        providerSample,
    }
}
</script>
