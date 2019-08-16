<template>
        <tr>
            <td v-if="!editando">{{ item.site }}</td>
            <td v-else><input type="text" v-model="item.site"></td>
            <td v-if="!editando">{{ item.user }}</td>
            <td v-else><input type="text" v-model="item.user"></td>
            <Oculto :valor="item.pass" v-if="!editando"></Oculto>
            <td v-else><input type="text" v-model="item.pass"></td>
            <td><img @click="editar" src="../assets/editar.png" alt="edit icon" class="icon">
                <img @click="deletar(item)" src="../assets/apagar.png" alt="delete icon" class="icon">
            </td>
        </tr>
</template>
<script>
    import Oculto from "@/components/Oculto"

    export default {
        name: 'LinhaTabela',
        components: {Oculto},
        props: {
            deletar: Function,
            item: Object,
        },
        data(){
            return{
                editando: false,
            }
        },
        methods:{
            editar(){
                this.editando = !this.editando
            },
        },
        computed:{
            editado(){
                if(this.editando){
                    return `<input>`
                }
                return this.item
            }
        }
    }
</script>
<style>
    .icon {
        height: 24px;
        width: 24px;
    }
    table {
        border-collapse: collapse;
    }

    table, th, td {
        border: 1px solid black;
    }
</style>