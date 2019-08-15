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
                <tr v-for="l in lista" :key="l.id">
                    <td>{{ l.site }}</td>
                    <td>{{ l.user }}</td>
                    <Oculto :valor="l.pass"></Oculto>
                    <td><img @click="editar(l)" src="../assets/editar.png" alt="edit icon" class="icon"> <img @click="deletar(l)" src="../assets/apagar.png" alt="delete icon" class="icon"></td>
                </tr>
            </tbody>
        </table>
    </div>
</template>

<script>
    import Oculto from "@/components/Oculto";
    export default {
        name: "Tabela",
        components: {Oculto},
        props:{
            lista: Array,
            editar: Function,
            deletar: Function,
        },
        filters:{
            ocultar(valor){
                return '***'
            }
        }
    }
</script>

<style>
    .icon{
        height: 24px;
        width: 24px;
    }
</style>