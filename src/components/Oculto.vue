<template>
    <td>{{ exibido }} <img @click="alternar" src="../assets/mostrar.png" alt="show icon" class="icon"></td>
</template>

<script>
    export default {
        name: "Oculto",
        props:{
            valor: String,
        },
        data() {
            return{
                exibindo: false
            }
        },
        computed:{
            exibido(){
                if(this.exibindo){
                    return this.valor
                }
                return "***"
            }
        },
        methods:{
            alternar(){
                this.exibindo = !this.exibindo
            }
        }
    }
</script>

<style scoped>

</style>