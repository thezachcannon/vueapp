<template>
  <div class='test'>
    <input type='text' v-model='title'>
    <br>
    <h1>{{title}} </h1>
    <p v-if='showName' v-text='user.first_name'></p>
    <p v-else='showName'>Nobody</p> 
    <ul>
      <li v-for='item in items'>{{item.title}}</li>
    </ul>
    <button v-on:click='greet("Hello World")'>Say Greeting</button>
    <br>
    <input type='text' v-on:keyup='pressKey'>
    
  </div>
</template>

<script>
  export default{
    name: 'test',
    data(){
      return {
        title: 'Hello World',
        user: {
          first_name: 'Zach',
          last_name: 'Cannon'
        },
        showName: true,
        items: [
          {title: 'Item One'},          
          {title: 'Item Two'},          
          {title: 'Item Three'}
        ]
      }
    },
    methods: {
      greet: function (greeting){
        alert(greeting);
      },
      pressKey: function (e){
        console.log(e.target.value)
      }
    }
  }
</script>
<style scoped>

</style>  