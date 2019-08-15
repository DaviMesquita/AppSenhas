<template>
        <label>
            {{ texto }}:
            <input :value="value" :type="tipo" @input="altera($event)">
        </label>
</template>
<script>
    export default {
        name: 'Campo',
        props: {
            texto: String,
            tipo: String,
            value: String,
        },
        methods: {
            altera($event){
                this.$emit('input', $event.target.value)
            }
        }
    }
</script>
