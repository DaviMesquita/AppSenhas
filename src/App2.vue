<template>
    <div id="app">
        <h1>Aula 14/08 | 15/08</h1>
        <Formulario :novo="novo" :salvar="salvar" :gerarSenha="gerarSenha"></Formulario>
        <Tabela :lista="lista" :deletar="deletar"></Tabela>
    </div>
</template>

<script>
    import Tabela from "@/components/Tabela";
    import Formulario from "@/components/Formulario";

    export default {
        name: "App2",
        components: {Formulario, Tabela},
        data() {
            return {
                novo: {
                    site: '',
                    user: '',
                    pass: '',
                },
                lista: [
                    {id: 1, site: 'gmail.com', user: 'davi@gmail.com', pass: 'd@gc'},
                    {id: 2, site: 'hotmail.com', user: 'davi@hotmail.com', pass: 'd@hc'},
                    {id: 3, site: 'github.com', user: 'davi.mesquita', pass: 'dghc'},
                ],
                count: 3,
            }
        },
        methods: {
            salvar() {
                this.lista.push({
                    ...this.novo,
                    id: ++this.count,
                })
                this.novo = {site: '', user: '', pass: '',}
            },
            deletar(l) {
                let index = this.lista.indexOf(l)
                this.$delete(this.lista, index)
            },
            gerarSenha() {
                const MAPA = 'abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ1234567890!@#$%¨&*()_+=-';
                let senha = '';
                for (let i = 0; i < 8; i++) {
                    senha += MAPA[
                        Math.floor(
                            Math.random() * MAPA.length
                        )]
                }
                this.novo.pass = senha
            },
        },
    }
</script>

<style scoped>

</style>