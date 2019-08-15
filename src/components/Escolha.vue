<template>
    <ul>
        <li v-for="cor in cores" :key="cor" @click="selecionar(cor)">{{ cor }}
         <span v-if="value === cor">*</span>
        </li>
    </ul>
</template>

<script>
    export default {
        name: "Escolha",
        props: {
            cores: Array,
            value: String,
        },
        methods: {
            selecionar(cor){
                this.$emit('input', cor)
            },
        },
    }
</script>

<style scoped>

</style>