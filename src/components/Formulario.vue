<template>
    <div>
        <Campo texto="Site" type="text" v-model="novo.site"/>
        <Campo texto="Usuário" type="text" v-model="novo.user"/>
        <Campo texto="Senha" type="password" v-model="novo.pass"/><button @click="gerarSenha">Gerar</button>
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

