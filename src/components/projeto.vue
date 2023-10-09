<template>
  <div class="content">
    
    <div class="left-side">
      <div class="agroup-content">
        <h2>EcoLogica</h2>
        <img src="CIPA.png" alt="" srcset="">
        
      
      </div>
    </div>
    


    <!-- Right side of the page-->
    <div class="right-side">
    <p>Por favor, Preencha o formulario para cadastrar seu projeto</p>
      
      <div id="inputs-group">
        <div class="input-group mb-3">
          <label for="exampleFormControlTextarea1" class="form-label">Nome do lider</label>
  <input type="text" class="form-control" placeholder="Username" aria-label="Username" aria-describedby="basic-addon1">
</div>
<div class="input-group mb-3">
          <label for="exampleFormControlTextarea1" class="form-label">Digite o valor:</label>
  <input type="text" class="form-control" placeholder="R$" aria-label="Username" aria-describedby="basic-addon1">
</div>
<div class="input-group mb-3">
  <label class="input-group-text" for="inputGroupSelect01">Tipo de Lixo:</label>
  <select class="form-select" id="inputGroupSelect01">
    <option selected>natureza</option>
    <option value="1">Sla</option>
    <option value="2">Oporra</option>
    <option value="3">Diabo 4</option>
  </select>
</div>
        <div class="mb-3">
          <label for="exampleFormControlTextarea1" class="form-label">Descreva seu projeto</label>
  <textarea class="form-control" id="exampleFormControlTextarea1" rows="3"></textarea>
</div>
      </div>
      <button type="button" class="btn btn-primary btn-lg" style="margin-bottom: 1%;">Cadastrar</button>
      <div id="passwordHelpBlock" class="form-text">
        Quer voltar a tela Inicial? <a @click="logar" style="color: blue;">Clique Aqui!</a>
      </div>
  </div>
  
  </div>
</template>

<style scoped>



.right-side p{
font-size: 15pt;
}
.senha1{
  width: 83%;
}
h2,p{
color: #1E2F40!important;
}.teste {
  width: 100%;
  height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  background-color: #F1F4FF;
  font-family: 'Red Hat Display', sans-serif!important;
}

.inputs{
  width: 80%;
  align-items: center;
  justify-content: center;
}

.content {
  width: 100%;
  height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  box-shadow: 0 8px 10px rgba(0, 0, 0, 0.1);
  border-radius: 42px;
  background-color: #F1F4FF;
  font-family: 'Red Hat Display', sans-serif!important;
}
.animato{
display: flex;
position: relative;
top: -50px;
width: 55px;
left: 86%;

}
.animato img:hover{
  cursor: pointer;
}

.left-side {
  width: 40%;
  height: 70%;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
  background-color: antiquewhite; 
  border-bottom-left-radius: 25px;
 border-top-left-radius: 25px;

}

.right-side {
  width: 40%;
  height: 70%;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  justify-items: center;
  border-left: 0.1rem solid black;
  background-color: antiquewhite;
  border-bottom-right-radius: 25px;
 border-top-right-radius: 25px;
}

.agroup-content img{
  width: 620px;
  margin-top: 10%;
}
.agroup-content h2{
  font-family: 'Red Hat Display', sans-serif;
  font-size: 50pt;
  margin-top: 15%;
}
.agroup-content p{
  font-family: 'Red Hat Display', sans-serif;
  font-size: 20pt;
}
.right-side img{
width: 270px;
animation: flutuar 2s ease-in-out infinite;
}

#inputs-group{
width: 100%!important;
display: flex;
flex-direction: column;
justify-content: center;
justify-items: center;
align-items: center;
}
.mb-3{
width: 80%!important;
}
.mb-3 input{
  width: 100%;
}
button{
background-color: #4AB7AA;
border: none;
color: #fff;
padding-left: 20px!important;
padding-right: 20px!important;
box-shadow: 0 8px 10px rgba(0, 0, 0, 0.1);
}
button:hover{
background-color: #1A314B!important;
animation: pulseAnimation 2s ease-in-out infinite!important;
}
a:hover{
  cursor: pointer!important;
}

@keyframes pulseAnimation {
  0% {
    transform: scale(1);
  }
  50% {
    transform: scale(1.1);
  }
  100% {
    transform: scale(1);
  }
}
@keyframes flutuar {
0% { transform: translateY(0); }
50% { transform: translateY(-20px); }
100% { transform: translateY(0); }
}
@keyframes pulse {
0% { transform: scale(1); }
50% { transform: scale(1.1); }
100% { transform: scale(1); }
}
</style>
<script>

export default {
  name: "login",
  data() {
    return {
      email: "",
      senha: "",
      emailValid: true,
      imageSrc: "C.png",
      showPassword: false,
    };
  },
  methods: {
    togglePasswordVisibility() {
    
    this.showPassword = !this.showPassword;
    if(this.showPassword == true && this.senha){
      this.imageSrc = "public/closed.png"
    }else if (this.showPassword == false && this.senha){
      this.imageSrc = "public/open.png"
    }else if(this.senha == ""){
      this.imageSrc = "public/c.png"
    }
   
  },
     logar() {
      
      this.$router.push("/home");

    },

    updateImage(){

     if(this.showPassword == true && this.senha){
      this.imageSrc = "public/closed.png"
    }else if (this.showPassword == false && this.senha){
      this.imageSrc = "public/open.png"
    }else if(this.senha == ""){
      this.imageSrc = "public/c.png"
    }

    },
    cadastre() {
      this.$router.push("cadastro");
    },
    recuperar() {
      return this.$router.push("/email");
    },
    checkEmail(){
      if (!this.email.endsWith('discente.ifpe.edu.br')) {
        this.emailIsValid = false;
      } else {
        this.emailIsValid = true;
      }
    }
  },


};
</script>
