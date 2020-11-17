<template>
  <div :class="{'selected':isSelected,'notselected': !isSelected}">
      <div class="nameArea">
         <h1>{{pessoa.nome}}</h1>
         <h1>{{pessoa.sobrenome}}</h1>
      </div>
      <div class="buttonsArea">
          <button class="delete" @click="select">Selecionar</button>
            <div class="img">
                <img src="../assets/delete.png" >
            </div>
      </div>
      
  </div>
</template>

<script>
export default {

    data(){
        return{
            isSelected:false
            }
    },

    props:{
       pessoa:Object
    },

    methods:{
        select: function(){
            this.isSelected = !this.isSelected
        }
    }

}
</script>

<style>

.notselected{
    display: flex;
    justify-self: center;
    align-self: center;

    background:#3DA6A8;

    border-radius:12px;
    height: 140px;
    padding:1rem;
    width: 600px;
    margin-top: 12px;
    color:#ffffff;
    transition: .4s;
}
.notselected:hover{
    transform: translateX(4%);
}


.nameArea{
    display: flex;
    flex-direction:column;
    justify-content:center;
    font-family: Roboto;
}

.buttonsArea{
    display: flex;
    justify-content: space-around;
    align-items: center;
    width: 650px;
}

.delete{
    width: 100px;
    border-radius: 0;
}

div.img{
    display: flex;
    justify-content: center;
    align-items: center;
    cursor: pointer;

    background: red;
    width: 28px;
    height: 28px;
    border-radius: 50%;
}

img{
    width: 20px;
    height: 20px;
    cursor:pointer;
    opacity: 0.6;
}

img:hover{
    opacity:1;
}

.buttonsArea button{
     align-self: center;

    width:6rem ;
    height: 2.4rem;
    border-radius: 10px;

    font-weight: bold;
    font-family: Roboto,sans-serif;

    background:#64c22e;
    transition: .3s;
}
.buttonsArea button:hover{
    background:#649746;
}

.selected{
    display: flex;
    justify-self: center;
    align-self: center;

    background:#649746;

    border-radius:12px;
    height: 140px;
    padding:1rem;
    width: 600px;
    margin-top: 12px;
    margin-left: 30px;
    color:#ffffff;

    transition: .4s;
}
.selected:hover{
    margin-left: 30px;
}

.selected button:hover{
    background:#5eff00;
}
</style>