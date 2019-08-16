<template>
    <div>
        <Campo texto="Site" tipo="text" v-model="novo.site"/>
        <Campo texto="Usuário" tipo="text" v-model="novo.user"/>
        <Campo texto="Senha" tipo="password" v-model="novo.pass"/><button @click="gerarSenha">Gerar</button>
        <button @click="salvar">Salvar</button>
    </div>
</template>

<script>
    import Campo from "@/components/Campo";

    export default {
        name: "Formulario",
        components: {Campo},
        props:{
            novo: Object,
            salvar: Function,
            gerarSenha: Function,
        }
    }
</script>

