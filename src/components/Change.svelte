<script>
	let ap = { avant: false };
    let ap1 = { avant1: false };


	function toggle() {
		ap.avant = !ap.avant;
	}
    function toggle1() {
        ap1.avant1 = !ap1.avant1;
	}

</script>

<div class="parent">
{#if ap.avant}
        <img on:click={toggle} src="https://www.pngplay.com/wp-content/uploads/12/Captain-America-The-First-Avenger-Background-PNG.png" alt="">
        <h2>Aprés</h2>

{/if}

{#if !ap.avant}
	
        <img on:click={toggle} src="https://www.pngmart.com/files/2/Captain-America-PNG-Pic.png" alt="">
        <h2>Avant</h2>

{/if}

{#if ap1.avant1}
		<img on:click={toggle1}  src="https://i.pinimg.com/originals/9d/28/ed/9d28ed4f08d480d51708e1213b8a94a2.png" alt="">
        <h2>Aprés</h2>
{/if}

{#if !ap1.avant1}
		<img on:click={toggle1} src="https://www.pngall.com/wp-content/uploads/2016/03/Hulk-Smash-Transparent-PNG.png" alt="">
        <h2>Avant</h2>
{/if}
</div>

<style>
  @import url("https://fonts.googleapis.com/css?family=Dekko|Lato:900|Rock+Salt");

    h2{
    font-family: "Dekko", cursive;
    }
    img{
    height: 156px;
    width: 176px;
    }
    .parent {
    display: grid;
    grid-template-columns: repeat(1, 1fr);
    grid-column-gap: 0px;
    grid-row-gap: 0px;
    height: 500px;
    justify-items: center;

    }
    button{
        background: none;
        
    }
</style>