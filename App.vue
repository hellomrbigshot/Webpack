<template>
    <h1>{{ msg }}</h1>
</template>

<script>
export default {
    data () {
        return {
            msg: 'Hello, Webpack'
        }
    }
}
</script>

<style scoped lang="scss">
    h1 {
        color: red;
    }
</style>
