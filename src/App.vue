<template>
  <div id="app">
    <Form/>
  </div>
</template>

<script>
import Form from './components/Form'


export default {
  name: 'App',
  components: {
    Form,
  }
}
</script>

<style>
body{
  background: #5EA6A0;
}
*{
  padding: 0;
  margin: 0;
  box-sizing: border-box;
}

button,input{
  outline: 0;
  border: 0;
}

button{
  cursor: pointer;
}

#app{
  display: flex;
  align-items: center;
  justify-content: center;
}
</style>
