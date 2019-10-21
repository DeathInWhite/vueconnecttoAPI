<template>
    <div>
        <tbody>
            <tr v-for="todo in pruebas" :key="todo.id">
                <td>{{todo.name}}</td>
                <td>{{todo.id}}</td>
            </tr>
        </tbody>
    </div>
</template>

<script>
import axios from 'axios'
export default {
    data(){
        return{
           todos:null,
           pruebas:null
        }
    },
    mounted(){
        this.getTodos();
        this.getPrueba();
    },
    methods:{
        getTodos(){
            axios.get('https://jsonplaceholder.typicode.com/todos').then(response =>{
              this.todos= response.data
            })
        },
        getPrueba(){
            axios.get('http://localhost:8000/languages/').then(response =>{
                this.pruebas = response.data
            })
        }
    }
}
</script>

<style>

</style>