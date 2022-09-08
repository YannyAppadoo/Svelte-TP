<script>

  //Parallax
  let scroll = 0


  // composant popup
  import Modal,{getModal} from '../src/components/Modal.svelte'
  import TodoList from './components/TodoList.svelte';
  import Compteur from './components/Compteur.svelte';
  import Alerte from './components/Alerte.svelte';
  import Change from './components/Change.svelte';
  import Animation from './components/Animation.svelte';

  import TodoListInfo from './components/TodoListInfo.svelte';
  import ModalInfo from './components/ModalInfo.svelte';
  import AlerteInfo from './components/AlerteInfo.svelte';
  import CompteurInfo from './components/CompteurInfo.svelte';
  import ChangeInfo from './components/ChangeInfo.svelte';
	
	let selection
	
	// Callback function provided to the `open` function, it receives the value given to the `close` function call, or `undefined` if the Modal was closed with escape or clicking the X, etc.
	function setSelection(res){
		selection=res
	}
  //composant popup


</script>


<svelte:window bind:scrollY={scroll}/>
<div id="container">
		<p class="comics">SVELTE <br> Composants réutilisables</p>
</div>


<br>


<div id="app"></div>

<article class="comic">

<!--PANEL TODO-->
  <div class="panel" style=";block-size: auto; padding: 31px; height:250px;">
    <img src="/src/assets/toile1.png" alt="toile" style=" height: 305px;
    position: absolute;
    top: -8px;
    left: 0%;
    z-index: 0;">
    <img src="/src/assets/spider.png" alt="spiderman" style=" height: 373px;position: absolute;top:-8px; left: 80%;">
    <!-- TODO-->
    <TodoList />
    <!-- TODO-->
    <TodoListInfo />
    <p class="text top-left">TodoList...</p>
    <p class="text bottom-right">...rempli t'es tâches</p>
  </div>

<!--PANEL POPUP-->
  <div class="panel" style="block-size: auto; padding: 31px; height: 290px; display: flex; align-items: center; justify-content: center; z-index: 40;">
    <img src="/src/assets/wolve.png" alt="wolverin" style=" height: 182px; position: absolute; top: 14px; left: 291px; z-index: 99;">
    <!-- POPUP-->
    <!-- Simplest use: modal without an `id` or callback function -->
      <button on:click={()=>getModal().open()}>
        Popup
      </button>

      <!-- the modal without an `id` -->
      <Modal>
        <button on:click={()=>getModal('second').open(setSelection)}>
          Second popup
        </button>
        {#if selection}
        <p>
          Your selection was: {selection}
        </p>
        {/if}
      </Modal>

      <Modal id="second">
        <img src="https://www.petitmerlin.com/7310/coton-popeline-masques-des-heros-marvel-sur-fond-vert-fonce-dapper-oekotex-100.jpg" alt="comics" style="height:300px">
      </Modal>
    <!-- POPUP-->
    <ModalInfo/>
    <p class="text top-left">Pop Up...</p>
    <p class="text bottom-right">...Click on me</p>
  </div>

  <!--PANEL COMPTEUR-->
  <div class="panel" style="block-size: auto; padding: 31px;">
    <Compteur/>
    <img src="/src/assets/poing.png" alt="" style=" height: 188px; position: absolute; top: 174px; left: -5%; z-index: 0;">
    <img src="/src/assets/hulk.png" alt="" style=" height: 251px; position: absolute; top: 13px;left: 343px;">
    <CompteurInfo/>
    <p class="text top-left">Compteur</p>
    <p class="text bottom-right">...HULK!!!!</p>
  </div>

  <!--PANEL BOX ALERTE-->
  <div class="panel" style="flex-basis: 290px;;block-size: auto; padding: 31px;z-index:9;">
    <Alerte />
    <AlerteInfo/>
    <img src="/src/assets/eclaire.png" alt="" style="height: 382px;position: absolute;top: -46px;left: 32%;z-index: -9;}">
    <img src="/src/assets/thor.png" alt="" style=" height: 317px; position: absolute; top: 206px;left: 68px;">
    <p class="text top-left">Alerte</p>
  </div>

  <div class="panel" style="flex-basis: 290px;;block-size: auto; padding: 31px;">
    <Change/>
    <ChangeInfo/>
    <p class="text top-left">Avant/Après</p>
  </div>




</article>








<style>



/* PARALLAX */
#app{
  padding: 0rem 1rem;
}

  #container {
		display: flex;
		align-items: center;
    justify-content: center;
    background-image: radial-gradient(circle, lightcoral, tomato);
    padding-top: 57px;
    border: 2px solid black;
}
	.text55 {
		font-weight: bold;
		color: #8C7A64;
		padding: 0 40px;
    font-size: 4rem;
    font-weight: bold;
    color: #fff;
    padding: 0 40px;
    line-height: 1.5;
    height: 400px;
    display: flex;
    align-items: center;
	}
  .comics {
		font-weight: bold;
		color: #8C7A64;
		padding: 0 40px;
    font-size: 4rem;
    font-weight: bold;
    color: #fff;
    padding: 0 40px;
    line-height: 1.5;
    border: 2px solid;
    display: flex;
    font-family: 'Passion One', impact;
    align-items: center;
	}
	.picture img {
		border-radius: 5px
	}
	


  /* POLICE COMICS*/
  @import url("https://fonts.googleapis.com/css?family=Dekko|Lato:900|Rock+Salt");
    /* POLICE BANGER*/
  @import url(https://fonts.googleapis.com/css?family=Bangers);
  @import url(https://fonts.googleapis.com/css?family=Passion+One);



  h1{
    color: rgb(235, 63, 0);
  }

  button {
    max-width: 500px;
    margin: 2rem 0;
    padding: 0.2rem 1.25rem;
    text-align: center;
    font-family: "Dekko", cursive;
    text-transform: uppercase;
    font-size: 2rem;
    letter-spacing: 0.2rem;
    background: url('data:image/svg+xml;utf8,<svg width="100" height="100" transform="rotate(25)" opacity="0.3" version="1.1" viewBox="0 0 100 100" xmlns="http://www.w3.org/2000/svg"><g  fill="%23250E17"><circle cx="25" cy="25" r="12.5"/><circle cx="75" cy="75" r="12.5"/><circle cx="75" cy="25" r="12.5"/><circle cx="25" cy="75" r="12.5"/></g></svg>'),
      #fff;
    background-size: 12px, 100%;
    border: 0.4rem solid #000;
    border-radius: 0px !important;
    position: relative;
  }
  button:before {
    content: "";
    position: absolute;
    left: -1rem;
    top: 0.15rem;
    width: 100%;
    height: 100%;
    background: url('data:image/svg+xml;utf8,<svg width="100" height="100" transform="rotate(35)" opacity="1" version="1.1" viewBox="0 0 100 100" xmlns="http://www.w3.org/2000/svg"><g fill="%23250E17"><circle cx="25" cy="25" r="12.5"/><circle cx="75" cy="75" r="12.5"/><circle cx="75" cy="25" r="12.5"/><circle cx="25" cy="75" r="12.5"/></g></svg>'),
      #000;
    background-size: 12px, 100%;
    border: 0.4rem solid #000;
    z-index: -5;
  }
  button {
    background: url('data:image/svg+xml;utf8,<svg width="100" height="100" transform="rotate(25)" opacity="0.8" version="1.1" viewBox="0 0 100 100" xmlns="http://www.w3.org/2000/svg"><g  fill="%23d68810"><circle cx="25" cy="25" r="12.5"/><circle cx="75" cy="75" r="12.5"/><circle cx="75" cy="25" r="12.5"/><circle cx="25" cy="75" r="12.5"/></g></svg>'),
      #ffcd28;
    background-size: 13px, 100%;
    font-weight: 700;
  }
  button {
    content: "!";
  }



    .green {
      background: #0f0;
    }
    html, body {
      margin:0;
      padding:0;
    }
    
    .comic {
      display:flex;
      flex-wrap:wrap;
      font-family:'Comic Sans', cursive;
      padding:1vmin;
    }
    
    .panel {
      background-color:#fff;
      border:solid 2px #000;
      box-shadow:0 6px 6px -6px #000;
      display:inline-block;
      flex:1 1;
      height:500px;
      margin:1vmin;
      overflow:hidden;
      position:relative;
    }
    
    .text {
      background-color:#fff;
      border:solid 2px #000;
      margin:0;
      padding:3px 10px;
      z-index: 9
    }
    
    .top-left {
      left:-6px;
      position:absolute;
      top:-2px;
      transform:skew(-15deg);
    }
    
    .bottom-right {
      bottom:-2px;
      position:absolute;
      right:-6px;
      transform:skew(-15deg);
    }
    
    .speech {
      background-color:#fff;
      border:solid 2px #000;
      border-radius:12px;
      display:inline-block;
      margin:.5em;
      padding:.5em 1em;
      position:relative;
    }
    
    .speech:before {
      border:solid 12px transparent;
      border-left:solid 12px #000;
      border-top:solid 12px #000;
      bottom:-24px;
      content:"";
      height:0;
      left:24px;
      position:absolute;
      transform:skew(-15deg);
      width:0;
    }
    
    .speech:after {
      border:solid 10px transparent;
      border-left:solid 10px #fff;
      border-top:solid 10px #fff;
      bottom:-19px;
      content:"";
      height:0;
      left:27px;
      position:absolute;
      transform:skew(-15deg);
      width:0;
    }
    
    .panel:nth-child(1) {
      flex-basis: 690px;
    }
    .panel:nth-child(2) {
      flex-basis: 426px;
    }
    .panel:nth-child(3) {
      flex-basis: 451px;
    }
    .panel:nth-child(4) {
      flex-basis: 200px;
    }
    .panel:nth-child(5) {
      flex-basis: 400px;
    }
    .panel:nth-child(6) {
      flex-basis: 200px;
    }
    .panel:nth-child(7) {
      flex-basis: 400px;
    }
    .panel:nth-child(8) {
      flex-basis: 200px;
    }
    .panel:nth-child(9) {
      flex-basis: 200px;
    }
    
    /* background colours */
    
    .panel:nth-child(4n+1) {
      background-image:radial-gradient(circle, yellow, orange);
    }
    
    .panel:nth-child(4n+2) {
      background-image:radial-gradient(circle, lightblue, deepskyblue);
    }
    
    .panel:nth-child(4n+3) {
      background-image:radial-gradient(circle, palegreen, yellowgreen);
    }
    
    .panel:nth-child(4n+4) {
      background-image:radial-gradient(circle, lightcoral, tomato);
    }

    
  </style>
