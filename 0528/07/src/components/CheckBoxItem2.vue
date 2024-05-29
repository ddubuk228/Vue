<template>
    <li>
        <input type="checkbox" :checked="checked">{{ idol.name }}
    </li>
</template>

<script>
    export default {
        name:"CheckBoxItem",
        props: ["idol"],
    }
</script>

<style scoped>

</style>