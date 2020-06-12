<template>
<div>
    <div>
        {{sharedState.reactiveStr}}
    </div>
    <providerGrandchild />
</div>
</template>

<script>
/*
20200613

provider,inject sampleです。
provideで定義した値を子や孫のコンポーネントに運搬します。
【親要素】
・provideで定義
・リアクティブな値はdata内でオブジェクトに内包する必要がある

【子・孫要素】
・inject:[XX]で定義
上記で定義した後はthis.XXとして使用可能
子要素以降で動的に値を変更した場合、親要素の値も変更される
*/
import providerGrandchild from './providerGrandchild.vue'
export default {
    components: {
        providerGrandchild
    },
    data() {
        return {
            sharedState: {
                reactiveStr: 'Hello'
            }
        }
    },
    mounted() {
        setTimeout(() => {
            this.sharedState.reactiveStr = "World";
        }, 3000);
    },
    provide() {
        return {
            //reactiveな値を子コンポーネントに渡すときは別オブジェクトで内包する必要がある
            ProviderGrandchild: '孫',
            ProviderReactive: this.sharedState
        }
    }
}
</script>
