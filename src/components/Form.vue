<template>
 <div>
     <div class="informations">

         <div class="formArea">
     
     <strong>Nome:</strong>
     <input type="text" v-model="nome">

     <strong>Sobrenome:</strong>
     <input type="text" v-model="sobrenome">

     <button @click="addPessoa">ADICIONAR</button>
         </div>

        <strong v-if="check" style="align-self:center;color:white;">PREENCHA OS CAMPOS</strong>
         <div v-for="pessoa in pessoas" :key="pessoa.nome">
            <Cards @deleteClient="deletando($event)" :pessoa="pessoa"/>
         </div>

     </div>
  
</div>
</template>

<script>
import Cards from './Cards'
export default {
    components:{
    Cards,
    },

    data(){
        return {
            check : false,

            pessoas:[
             
            ],

        nome:'',
        sobrenome:'',
                    
}
    },

    methods:{
        addPessoa: function(){
            
            if(this.nome === '' || this.sobrenome === ''){
                return this.check = true
            }

            this.pessoas.push({
                nome:this.nome,
                sobrenome:this.sobrenome
            ,})

            this.nome = ''
            this.sobrenome = ''
             return this.check = false   
        },

        deletando: function($event){
            const name = $event.personName
            
              const newPessoas =  this.pessoas.filter(pessoa => name !== pessoa.nome )

              this.pessoas = newPessoas
            }

            
        
    }
} 
</script>

<style>

.informations{
    background:#49230b;
    display: flex;
    flex-direction: column;
    justify-content: space-around;

    border-radius: 10px;
    margin-top: 5vh;
    padding: 1rem;
    width: 50vw;
    height: 100%;
    color: white;
}

.formArea{
    display:flex;
    flex-direction:column;
    justify-content: space-between;
    align-self: center;

    width: 20rem;
    height: 50vh;
    padding: 2rem;
}

input{
    align-self: center;

    height: 3rem;
    border-radius:10px ;
    padding: 0.5rem;

    font-family: sans-serif;
    font-weight: 500;
    font-family: Roboto,sans-serif;
    font-size: 13pt;

    margin-bottom:19px;
    transition: .3s;
}

input:hover{
    background: rgb(245, 245, 245);
}

strong{
    color:#71F1F5;
}

.formArea button{
    align-self: center;

    width:8rem ;
    height: 3rem;
    border-radius: 10px;

    font-weight: bold;
    font-family: Roboto,sans-serif;

    background:#71F1F5;
    transition: .3s;
}

.formArea button:hover{
background:#53dee0;
}
</style>