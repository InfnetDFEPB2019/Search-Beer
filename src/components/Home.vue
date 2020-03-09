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
            <b-button size="sm" class="my-2 my-sm-0" type="submit" >Pesquisar</b-button>
            
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

      <h1>Bem vindo as {{title}}</h1>

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
        
    <h2>
        SEARCH BEER
    </h2>
    <div>
        <div v-bind:key="cerveja.id" v-for="cerveja in cervejarias">
                
            <div>{{cerveja.name}}</div>
            <div>{{cerveja.city}}</div>
            <div>{{cerveja.website_url}}</div>
            <div>{{cerveja.updated_at}}</div>
        </div>
    </div>
   
  </div>
</template>

<script>
  export default {
    name: 'Home', 
    data: function(){
      return {
        title:"Cervejarias disponíveis próximo de sua localização",
        horas: new Date().getHours(),
        mostrarCervejarias: true,

        cervejarias: 
            [{"id":2,"name":"Avondale Brewing Co","brewery_type":"micro","street":"201 41st St S","city":"Birmingham","state":"Alabama","postal_code":"35222-1932","country":"United States","longitude":"-86.774322","latitude":"33.524521","phone":"2057775456","website_url":"http://www.avondalebrewing.com","updated_at":"2018-08-23T23:19:57.825Z","tag_list":[]},
            {"id":44,"name":"Trim Tab Brewing","brewery_type":"micro","street":"2721 5th Ave S","city":"Birmingham","state":"Alabama","postal_code":"35233-3401","country":"United States","longitude":"-86.7914000624146","latitude":"33.5128492349817","phone":"2057030536","website_url":"http://www.trimtabbrewing.com","updated_at":"2018-08-23T23:20:31.423Z","tag_list":[]},
            {"id":46,"name":"Yellowhammer Brewery","brewery_type":"micro","street":"2600 Clinton Ave W","city":"Huntsville","state":"Alabama","postal_code":"35805-3046","country":"United States","longitude":"-86.5932014","latitude":"34.7277523","phone":"2569755950","website_url":"http://www.yellowhammerbrewery.com","updated_at":"2018-08-23T23:20:33.102Z","tag_list":[]},
            {"id":55,"name":"Bearpaw River Brewing Co","brewery_type":"micro","street":"4605 E Palmer Wasilla Hwy","city":"Wasilla","state":"Alaska","postal_code":"99654-7679","country":"United States","longitude":"-149.4127103","latitude":"61.5752695","phone":"","website_url":"http://bearpawriverbrewing.com","updated_at":"2018-08-23T23:20:40.743Z","tag_list":[]},
            {"id":76,"name":"King Street Brewing Co","brewery_type":"micro","street":"9050 King Street","city":"Anchorage","state":"Alaska","postal_code":"99515","country":"United States","longitude":"-149.879076042937","latitude":"61.1384893547315","phone":"9073365464","website_url":"http://www.kingstreetbrewing.com","updated_at":"2018-08-23T23:20:57.179Z","tag_list":[]},
            {"id":94,"name":"1912 Brewing","brewery_type":"micro","street":"2045 N Forbes Blvd Ste 105","city":"Tucson","state":"Arizona","postal_code":"85745-1444","country":"United States","longitude":"-110.992750525872","latitude":"32.2467372722906","phone":"5202564851","website_url":"http://www.1912brewing.com","updated_at":"2018-08-23T23:21:11.302Z","tag_list":[]},
            {"id":98,"name":"Bad Water Brewing","brewery_type":"contract","street":"4216 N Brown Ave","city":"Scottsdale","state":"Arizona","postal_code":"85251-3914","country":"United States","longitude":"-111.924474347826","latitude":"33.4972615652174","phone":"5207459175","website_url":"http://www.badwaterbrewing.com","updated_at":"2018-08-23T23:21:15.169Z","tag_list":[]},
            {"id":104,"name":"BJs Restaurant \u0026 Brewery - Chandler","brewery_type":"brewpub","street":"3155 W Chandler Blvd","city":"Chandler","state":"Arizona","postal_code":"85226-5175","country":"United States","longitude":"-111.911126","latitude":"33.3053455","phone":"4809170631","website_url":"http://www.bjsrestaurants.com","updated_at":"2018-08-23T23:21:21.165Z","tag_list":[]},
            {"id":107,"name":"BlackRock Brewers","brewery_type":"micro","street":"1664 S Research Loop Ste 200","city":"Tucson","state":"Arizona","postal_code":"85710-6767","country":"United States","longitude":"-110.821778571134","latitude":"32.201608314954","phone":"5202073203","website_url":"http://www.brb.beer","updated_at":"2018-08-23T23:21:23.794Z","tag_list":[]},
            {"id":127,"name":"Dragoon Brewing Co","brewery_type":"micro","street":"1859 W Grant Rd Ste 111","city":"Tucson","state":"Arizona","postal_code":"85745-1214","country":"United States","longitude":"-111.005452051979","latitude":"32.2504946147872","phone":"5203293606","website_url":"http://www.dragoonbrewing.com","updated_at":"2018-08-23T23:21:40.563Z","tag_list":[]},
            {"id":141,"name":"Grand Canyon Brewing Company","brewery_type":"micro","street":"233 W Route 66","city":"Williams","state":"Arizona","postal_code":"86046-2530","country":"United States","longitude":"-112.1892168","latitude":"35.2500282","phone":"8005132072","website_url":"http://www.grandcanyonbrewingco.com","updated_at":"2018-08-23T23:21:53.397Z","tag_list":[]},
            {"id":163,"name":"Mudshark Brewing Co","brewery_type":"micro","street":"210 Swanson Ave","city":"Lake Havasu City","state":"Arizona","postal_code":"86403-0966","country":"United States","longitude":"-114.342433477881","latitude":"34.4689736300844","phone":"9284532981","website_url":"http://www.mudsharkbrewingco.com","updated_at":"2018-08-23T23:22:12.542Z","tag_list":[]},
            {"id":182,"name":"Richter Aleworks","brewery_type":"micro","street":"8279 W Lake Pleasant Pkwy Ste 110","city":"Peoria","state":"Arizona","postal_code":"85382-7434","country":"United States","longitude":"-112.238054093359","latitude":"33.6687744976834","phone":"6029086553","website_url":"http://www.richteraleworks.com","updated_at":"2018-08-23T23:22:29.385Z","tag_list":[]},
            {"id":187,"name":"SanTan Brewing Co","brewery_type":"regional","street":"8 S San Marcos Pl","city":"Chandler","state":"Arizona","postal_code":"85225-7862","country":"United States","longitude":"-111.8423459","latitude":"33.3032436","phone":"4809178700","website_url":"http://www.santanbrewing.com","updated_at":"2018-08-23T23:22:33.482Z","tag_list":[]},
            {"id":198,"name":"State 48 Brewery","brewery_type":"brewpub","street":"13823 W Bell Rd","city":"Surprise","state":"Arizona","postal_code":"85374-3873","country":"United States","longitude":"-112.357813820157","latitude":"33.63822125","phone":"6235841095","website_url":"","updated_at":"2018-08-23T23:22:41.468Z","tag_list":[]},
            {"id":219,"name":"Wren House Brewing Company","brewery_type":"micro","street":"2125 N 24th St","city":"Phoenix","state":"Arizona","postal_code":"85008-2713","country":"United States","longitude":"-112.0301125","latitude":"33.516633","phone":"6022449184","website_url":"http://www.wrenhousebrewing.com","updated_at":"2018-08-23T23:22:59.255Z","tag_list":[]},
            {"id":225,"name":"Brick Oven Pizza Co / Brick \u0026 Forge Brewing","brewery_type":"brewpub","street":"2410 Linwood Dr","city":"Paragould","state":"Arkansas","postal_code":"72450-6122","country":"United States","longitude":"-90.5204797204622","latitude":"36.0316358142169","phone":"8702364200","website_url":"http://www.brickovenpizzacompany.com","updated_at":"2018-08-23T23:23:05.438Z","tag_list":[]},
            {"id":235,"name":"Diamond Bear Brewing Co","brewery_type":"micro","street":"600 N Broadway St","city":"North Little Rock","state":"Arkansas","postal_code":"72114-5381","country":"United States","longitude":"-92.2726892120821","latitude":"34.7594277548278","phone":"5017082739","website_url":"http://www.diamondbear.com","updated_at":"2018-08-23T23:23:14.931Z","tag_list":[]},
            {"id":247,"name":"Lost Forty Brewing","brewery_type":"micro","street":"501 Byrd St","city":"Little Rock","state":"Arkansas","postal_code":"72202","country":"United States","longitude":"-92.260019","latitude":"34.742845","phone":"5013197275","website_url":"http://www.lost40brewing.com/","updated_at":"2018-08-23T23:23:24.018Z","tag_list":[]},
            {"id":253,"name":"Rapp's Barren Brewing Company","brewery_type":"micro","street":"1343 E 9th St","city":"Mountain Home","state":"Arkansas","postal_code":"72653-5050","country":"United States","longitude":"-92.3599724","latitude":"36.3326432","phone":"8704247288","website_url":"http://www.rappsbarrenbrewing.com","updated_at":"2018-08-23T23:23:29.428Z","tag_list":[]}],
        
      }
    },
  
    methods: {
      mostrarBusca(){
        this.mostrarCervejarias = this.mostrarCervejarias ? false: true;
      }
    },
  };

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
    transform: skew(0, 0deg);
}

h2 {
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
