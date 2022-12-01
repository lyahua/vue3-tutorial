<template>
    <div>
        1111
        <h2>姓名:{{ obj.name }}</h2>
        <h2>年龄:{{ obj.age }}</h2>

        <h2>姓名2:{{ name }}</h2>

        <button @click="changeName">改变姓名</button>
    </div>
</template>

<script>
import { onBeforeMount, onBeforeUnmount, onBeforeUpdate, onMounted, onUnmounted, onUpdated, reactive, ref } from 'vue';
export default {
    setup() {
        const obj = reactive({ name: 'zs', age: 18 })
        const name = ref(obj.name)

        const changeName = () => {
            obj.name = 'ls'
            name.value = '0000'
        }

        onBeforeMount(() => {
            console.log('onBeforeMount')
        })

        onMounted(() => {
            console.log('onMounted')
        })

        onBeforeUpdate(() => {
            console.log('onBeforeUpdate')
        })

        onUpdated(() => {
            console.log('onUpdated')
        })

        onBeforeUnmount(() => {
            console.log('onBeforeUnmount')
        })

        onUnmounted(() => {
            console.log('onUnmounted')
        })

        return { obj, name, changeName }
    }
}
</script>

<style lang="less" scoped>

</style>