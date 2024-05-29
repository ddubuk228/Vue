<template>
    <li>
        <input type="checkbox" :checked="idol.checked">{{ idol.name }}
    </li>
</template>

<script>
import idol from '../idol';
    export default {
        name:"CheckBoxItem3",
        props: {
            idol: idol,
        },
    }
</script>

<style scoped>

</style>