<template>
  <div class="hello">

    <div>
    <b-navbar toggleable="lg" type="dark" variant="info">
        <b-navbar-brand href="#">Search-Beer</b-navbar-brand>

        <b-navbar-toggle target="nav-collapse"></b-navbar-toggle>

        <b-collapse id="nav-collapse" is-nav>
        <b-navbar-nav>
            <b-nav-item href="#">Grupo</b-nav-item>
            <b-nav-item href="#" disabled>Contato</b-nav-item>
        </b-navbar-nav>

        <!-- Right aligned nav items -->
        <b-navbar-nav class="ml-auto">
            <b-nav-form>
            <b-form-input size="sm" class="mr-sm-2" placeholder="Search"></b-form-input>
            <b-button size="sm" class="my-2 my-sm-0" type="submit">Pesquisar</b-button>
            </b-nav-form>

            <b-nav-item-dropdown text="Linguagem" right>
            <b-dropdown-item href="#">PT-BR</b-dropdown-item>
            <b-dropdown-item href="#">ES</b-dropdown-item>
            <b-dropdown-item href="#">RU</b-dropdown-item>
            <b-dropdown-item href="#">FA</b-dropdown-item>
            </b-nav-item-dropdown>

            <b-nav-item-dropdown right>
            <!-- Using 'button-content' slot -->
            <template v-slot:button-content>
                <em>Login</em>
            </template>
            <b-dropdown-item href="#">Logar</b-dropdown-item>
            <b-dropdown-item href="#">Sair</b-dropdown-item>
            </b-nav-item-dropdown>
        </b-navbar-nav>
        </b-collapse>
    </b-navbar>
    </div>    

    <section class="fundo">
        <div id="action">
            <div id="keg">
                <div id="pipe-handle"></div>
                <div id="pipe"></div>       
                <div id="pipe-front"></div>
            </div>
        
            <div class="glass">
                <div class="beer"></div>
                <div class="handle">
                    <div class="top-right"></div>
                    <div class="bottom-right"></div>
                </div>
                <div class="front-glass"></div>
            </div>
        </div>
    </section>
        
    <h1>
        SEARCH BEER
    </h1>
   
  </div>
</template>

<script>
export default {
  name: 'Home',
  props: {
    msg: String
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

.mr-sm-2{
    background: #434A54;
}


body {
    margin: 0;
    padding: 0;
    font-family: sans-serif;
    background-color:  black;
    text-align: center;
}
h1 {
    display: inline-block;
    margin-top: 50px;
    color: rgb(221, 169, 0);
    border-top: solid 5px rgb(221, 169, 0);
    border-bottom: solid 5px rgb(221, 169, 0);
    transform: skew(0, -5deg);
}

.hello{
    background: black;
}

section {
     background-color: #0000;
}
#action {
    margin: 0 auto;
    width: 700px;
    position: relative;
    height: 300px;
   
}

#keg {
    position: absolute;
    height: 200px;    
    width: 70px;
    background-color: #656D78;
    border-right: solid 20px #434A54;
    bottom: 0;
    left: 310px;
}
#pipe {
    position: absolute;
    height: 30px;
    width: 10px;
    top: 30px;
    left: 10px;
    background-color: #CCD1D9;
}

#pipe:before {
    position: absolute;
    display: block;
    content: " ";
    height: 20px;
    width: 30px;
    top: -5px;
    left: 5px;
    background: linear-gradient(to bottom, #CCD1D9 50%, #AAB2BD 50%);
    border-radius: 0 10px 10px 0;
}

#pipe:after {
    position: absolute;
    display: block;
    content: " ";
    width: 10px;
    background-color: rgba(255, 206, 84, 0.5);
    
    animation: flow 5s ease infinite;
}

@keyframes flow {
    0%, 15% { 
        top: 30px;
        height: 0px;
    }
    20% { 
         height: 125px;
    }
    40% {        
        top: 30px;
        height: 85px;
    }
    55% {
        top: 30px;
        height: 60px;
    }
    60%, 100% {
        top: 70px;
        height: 0px;
    }
}

#pipe-front {
    position: absolute;
    height: 14px;
    width: 14px;
    top: 25px;
    left: 5px;
    background-color: #F5F7FA;
    border-radius: 10px;
    border: solid 3px #CCD1D9;
}

#pipe-handle {
    transform-origin: center bottom;
    position: absolute;
    width: 0;
    height: 5px;
    top: -20px;
    left: 5px;
    border-style: solid;
    border-width: 50px 10px 0 10px;
    border-color: black transparent transparent transparent;
    
    animation: handle 5s ease infinite;    
}
#pipe-handle:before {
    position: absolute;
    top: -60px;
    left: -10px;
    display: block;
    content: ' ';
    width: 20px;
    height: 10px;
    background-color: #CCD1D9;
    border-radius: 5px 5px 0 0;
}
#pipe-handle:after {
    position: absolute;
    top: -20px;
    left: -5px;
    display: block;
    content: ' ';
    width: 10px;
    height: 20px;
    background-color: #CCD1D9;
}

@keyframes handle {
    0%, 10% { 
       transform: rotate(0deg);
    }
    20%, 50% { 
         transform: rotate(-90deg);
    }
    60%, 100% {
        transform: rotate(0deg);
    }
}

.glass {    
    position: absolute;
    height: 100px;
    width: 70px;
    bottom: 0;
    background-color: rgba(255, 255, 255, 0.0);
    border-radius: 5px;
    
    animation: slide 5s ease forwards infinite;
}

@keyframes slide {
    0% { 
        opacity: 0;
        left: 0; 
    }
    20%, 80% { 
        opacity: 1;
        left: 300px; 
    }
    100% {
         opacity: 0;
        left: 600px;
    }
}

.front-glass {
    position: relative;
    height: 100%;
    width: 100%;
    background-color: rgba(255, 255, 255, 0.3);   
    border-radius: 5px;
}

.beer {
    position: absolute;
    bottom: 15px;
    margin: 0 5px;
    /*height: 80%;*/
    width: 60px;
    background-color: rgba(255, 206, 84, 0.8); /* #FFCE54*/
    border-radius: 0 0 5px 5px;
    border-top: solid 0px rgba(255, 206, 84, 0.8);
    
    animation: fillup 5s ease infinite;
}
.beer:after {
    position: absolute;
    display: block;
    content: " ";
    /*height: 20px;*/
    width: 100%;
    background-color: white;
    /*top: -20px;*/
    border-radius: 5px 5px 0 0;
    
    animation: fillupfoam 5s linear infinite, wave 0.5s alternate infinite;
}

.handle {
    position: absolute;
    right: -20px;
    top: 20px;
}
.handle .top-right {
    height: 20px;
    width: 10px;
    border-top: solid 10px rgba(255, 255, 255, 0.4);
    border-right: solid 10px rgba(255, 255, 255, 0.4);
    border-top-right-radius: 20px;
}
.handle .bottom-right {
    height: 20px;
    width: 10px;
    border-bottom: solid 10px rgba(255, 255, 255, 0.4);
    border-right: solid 10px rgba(255, 255, 255, 0.4);
    border-bottom-right-radius: 20px;
}

@keyframes fillup {
    0%, 20% { 
        height: 0px; 
        border-width: 0px;
    }
    40% {
        height: 40px; 
    }
    80%, 100% { 
        height: 80px; 
        border-width: 5px;
    }
}
@keyframes fillupfoam {
    0%, 20% { 
        top: 0px;
        height: 0px; 
    }
    60%, 100% { 
        top: -14px;
        height: 15px; 
    }
}
@keyframes wave {
    from { 
        transform: skew(0, -3deg);
    }
    to { 
        transform: skew(0, 3deg);
    }
}

</style>
