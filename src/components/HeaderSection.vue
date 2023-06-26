<template>
    <h1>Student Cards</h1>
        <div class="grid">
            <div class="card" style="width: 18rem" v-for="user in student" :key="user.id">
                <img src="https://images.pexels.com/photos/15286/pexels-photo.jpg?auto=compress&cs=tinysrgb&w=1260&h=750&dpr=1" style="width: 100%" alt="">
                <div class="card-body">
                    <h3>{{user.id}}. {{user.first_name}}</h3>
                    <p>{{user.email}}</p>
                </div>
            </div>  
        </div>
</template>

<script>
import axios from 'axios'
    export default {
        data(){
            return{
                student: []
            }
        },
        async mounted(){
            const getData = await axios.get('https://lc1007.github.io/jsonServer-Exercise/users.json')
            this.student = getData.data.students  
        }
    }
</script>

<style scoped>
    h1{
        text-align: center;
        margin: 4rem;
    }
    .grid{
        display: grid;
        grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
        place-items: center;
        gap: 1rem;
    }
    .card{
        margin: 1rem;
    }
</style>