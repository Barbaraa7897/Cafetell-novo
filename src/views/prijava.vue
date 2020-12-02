<template>
  
     <div class="hero-image1">
    <div>
    <h1 class="text-center mb-5" >Prijava</h1>
    </div>
     <form @submit.prevent="signin">
       <div class="kontejner">
       <div class="form-group">
          <label class="forma" for="korisnicko_ime">Korisničko ime</label> <br><br>
          <input v-model="email" type="email" class="form-control" id="emailField" aria-describedby="emailHelp"><br><br> 
       </div>
       <br>
       <div class="form-group">
          <label class="forma" for="passwordField">Lozinka</label> <br><br>
          <input v-model="password" type="lozinka" class="form-control" id="passwordField"><br><br>  
       </div> <br> 
       <div class="form-group">
       <button type="submit" class="prijava">Prijava</button>  
       <router-link to="/registracija"><h5>Niste registrirani?</h5></router-link>
       </div>
       </div>
       </form>
       </div>

       
       
</template>
<script>

export default {
  data () {
    return {
      email: '',
      password: ''
    }
  },
  methods: {
    signin () {
      firebase.auth().signInWithEmailAndPassword(this.email, this.password).catch(function(error) {
        console.log(error);
      });
    }
  }
}
</script> 


<style>
.form-control {

  background:transparent;
  border:none;
  border-bottom: 1px solid #000000;
  font-size: 1.5em;
  display:block;
  width:100%;
}

.forma {

font-size: 2em;
float:left;
color:#000000;
display:block;
}

.kontejner { 
  display:inline-block;
  width:30%;
  margin:auto;
}

.text-center {

font-size: 4em;

}

.prijava {

border-radius: 10px;
border: 1px solid;
padding: 10px;
font-size: 20px;

}

.hero-image1{
  background-image: url("/assets/zrnca2.jpg");
  background-size:cover;
  background-repeat: no-repeat;
  max-width: 100%;
  width:100%;
  min-height:100%;
  position: absolute;
  -webkit-background-size: cover;
  -moz-background-size: cover;
  -o-background-size: cover;
  background-size: cover;
}
.form-group{
  display:inline-block;
  width:100%;
}
</style>