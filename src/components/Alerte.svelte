<script>
	
	import { fade } from "svelte/transition";
	
	let show = false
	let showTimeout = ''
	
	let openNotification = () => {
		show = true
		showTimeout = setTimeout( () => { show = false }, 5000 );
	}
	
	let closeNotification = () => {
		show = false
		clearTimeout(showTimeout)
	}

</script>


<div id="container">
	<button on:click={openNotification}>Alerte !</button>
	{#if (show) }
		<div class="notification" transition:fade>
			Hello ! <br> Je vais disparaître dans 5 secondes. <br> A moins que tu me fermes avant ?
			<button class="croix" on:click="{closeNotification}">
			❌
			</button>
		</div>
	{/if}
    </div>


<style>
	#container {
	display: flex;
  	align-items: start;
  	justify-content: center;
	height: 100%;
	}
	.notification {
		min-width: 250px;
		margin-left: -125px;
		background-color: #e8eb34;
		color: #111;
		text-align: center;
		border-radius: 2px;
		padding: 16px;
		position: fixed;
		z-index: 999;
		left: 50%;
		top: 80px;
		font-size: 0.9rem;
	}
	.notification button {
		position: absolute;
		top: -68px;
		background-color: #e8eb34;
		border: 0;
	}
	button {
    max-width: 500px;
    margin: 2rem 0;
    padding: 0.2rem 1.25rem;
    text-align: start;
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
  /* for the highlight container always add an exclamation point */
  button {
    content: "!";
  }
  .croix{
    background: none;
	border: none;
  }
  .croix:before{
    background: none;
	border: none;
  }


</style>