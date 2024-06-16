<template>
    <div style="border: 1px soild gray; padding:5px">
        이름 : <input type="text" v-model="name" />
        <button @click="$emit('nameChanged', {name})">이벤트 발신</button>
    </div>
</template>

<script>
    export default {
        name: "InputName",
        //emits: ["nameChange1"],
        emits: {
            nameChanged: (e) => {
                return e.name && typeof(e.name) === "string" && e.name.trim().length >= 3
                ? true : false
            }
        },
        date(){
            return{ name: "" };
        },
        
    }
</script>

<style scoped>

</style>