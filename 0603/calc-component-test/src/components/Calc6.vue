<template>
    <div>
        X : <input type="text" v-model.number="state.x"><br />
        <div>결과 : {{ state.result }}</div>
    </div>
</template>

<script>
    import { watch, reactive } from 'vue'

    export default {
        name: "Calc5",
        setup() {
            const state = reactive({x:0, result:0});
            watch(() => state.x, (current, old) => {
                console.log(`${old} ==> ${current}`)
                state.result = current *2;
            })
            return { state }
        }
    }
</script>

<style scoped>

</style>