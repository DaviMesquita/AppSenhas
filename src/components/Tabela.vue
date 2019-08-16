<template>
    <div>
        <table>
            <thead>
                <tr>
                    <th>Site</th>
                    <th>Usuário</th>
                    <th>Senha</th>
                    <th></th>
                </tr>
            </thead>
            <tbody>
            <LinhaTabela :item="item" :deletar="deletar" editar="editar" v-for="item in lista" :key="item.id"/>
            </tbody>
        </table>
    </div>
</template>

<script>
    import LinhaTabela from "@/components/LinhaTabela";

    export default {
        name: "Tabela",
        components: {LinhaTabela},
        props:{
            lista: Array,
            deletar: Function,
        },
        filters:{
            // eslint-disable-next-line no-unused-vars
            ocultar(valor){
                return '***'
            }
        }
    }
</script>

