<template>
  <label for="message">write your message:</label><br>
  <input type="tex" placeholder="enter your message" id="message" v-model=" content">
  <button @click="addpost" >add</button>
  <post v-for="post in posts" :key="post.content" :content="post.content"/>
</template>
<script>
  import post from './components/post.vue'
  export default {
    name:'app', 
    data(){
        return{
          content: '',
          posts:[],
        }
    }, 
    components:{
      post
    },
    methods:{
      addpost:function(){
          this.posts.push({
            content:this.content
          })
          this.content =''
      }
    }
  }
</script>
<style>
  input{
    padding: 8px 10px;
    width: 50%;
    border: none;
    background-color: brown;
    color: white;
    outline: none;
    border-radius: 11px;
  }
  input::placeholder{
    color: white;
  }
  button{
    margin-left: 15px;
    padding: 6px 25px;
    text-transform: uppercase;
    background-color: #a52a2a;
    color: white;
    border: 0;
    border-radius: 10px;
    cursor: pointer;
    transition: all .3s;
  }
  button:hover{
    background-color: darkblue;
    transition: all .3s;
    transform: scale(1.2);
  }
  label{
    text-transform: capitalize;
    font-weight: 600;
    padding: 5px;
  }
  button,input{
    margin-top: 10px;
  }
</style>