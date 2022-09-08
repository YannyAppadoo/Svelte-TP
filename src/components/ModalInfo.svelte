<script>
	let modalState = 'none';
	let openModal = () => {
		modalState = 'block'
	}
	let closeModal = (e) => {
		if ( 
			( modalState == 'block' && 
			( e.target.parentElement.id !== 'modal-content' && e.target.id !== 'modal-content' ) &&
			e.target.id !== 'openButton' ) || 
			e.target.id == 'closeCross'
		) {
			modalState = 'none'
		}
	}
</script>

<svelte:window on:click={closeModal} />
<button id="openButton" on:click={openModal}>!</button>
<div id="modal" class="modal" style="--modal-state: {modalState}">
	<div id="modal-content" class="modal-content">
		<span id="closeCross" class="close" on:click={closeModal}>&times;</span>
		<h2>Pop Up</h2>
		<p>
            Une modal permet d'afficher des informations supplémentaires dans votre page, sous la forme d'une fenêtre. Celle-ci apparaitra lorsque l'utilisateur cliquera sur un lien particulier de la page.            <br>
			Cette modale s'ouvre lorsque l'on clique sur un bouton. Elle se ferme soit en cliquant sur une croix positionnée en haut à droite de la modale soit en cliquant à l'exterieur de la modale.
			Ouverture et fermeture du model (openModal et closemodal)
		</p>
	</div>
</div>


<style>
	.modal {
		display: var(--modal-state);
		position: fixed; 
		z-index: 1; 
		padding-top: 25%;
		left: 0;
		top: 0;
		width: 100%; 
		height: 100%; 
		overflow: auto; 
		background-color: rgba(0,0,0,0.4);
        z-index: 99;
	}
	.modal-content {
		background-color: #fefefe;
		margin: auto;
		padding: 20px;
		border: 1px solid #888;
		width: 80%;
		z-index: 999;
	}
	.close {
		color: #aaa;
		float: right;
		font-size: 28px;
		font-weight: bold;
		line-height: 0;
		margin-top:5px;
	}
	.close:hover,
	.close:focus {
		color: black;
		text-decoration: none;
		cursor: pointer;
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
    border: 0.2rem solid #000;
    border-radius: 0px !important;
    position: relative;
	background-color: #58ccf3;

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
    border: 0.2rem solid #000;
    z-index: -5;
  }
  button {
    background-size: 13px, 100%;
    font-weight: 700;
    position: absolute;
    left: 1px;
    top: 246px;
    border-radius: 50%;
  }
  button {
    content: "!";
  }
</style>