<template>
<div>
    <h2> CREATE POST</h2>
    <form @submit.prevent=onCreatePost>
        <div class="form-group">
            <label for="">TITLE</label>
            <input type="text" class="form-control"/> 
        </div>
        <div class="form-group">
            <label for="">DESCRIPTION</label>
            <textarea class="form-control"></textarea>
        </div>

        <div class="mt-3">
            <button type="submit" class="btn btn-primary">Create Post</button>
        </div>

    </form>
    <div v-for="post in posts" :key="post.title">
    <h2> {{ post.title }}</h2>
  </div>
</div>
</template>
<script>
import axios from 'axios';
let request = new XMLHttpRequest();
export default {
    data(){
        return{
            title:'',
            description:'',
            posts: []
            }
    },
    methods: {
        onCreatePost(){
            const data = {
             title : this.title,
                description : this.description}
            //    request.setRequestHeader('Content-Type','application/json');
              request.open("POST", "http://localhost:7500/static/Post-Post");   
           axios.post(`http://localhost:7500/static/Post-Post`,{
            data}).then(response=>{
            console.log(response)
            this.posts = response.data
            }
            ).catch(error => {
        if (!error.response) {
            // network error
            this.errorStatus = 'Error: Network Error';
        } else {
            this.errorStatus = error.response.data;
        }
      })
        }
    }

}
</script>