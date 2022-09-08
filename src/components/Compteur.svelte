<script>
	let text =''
	let result = 0
	$: result = text.length
</script>


<div id="container">
	<div class="child">
		<textarea bind:value={text} placeholder="Enter your text ..."></textarea>
		<div class="result">
			{result}
		</div>
	</div>
</div >



<style>
     /* POLICE COMICS*/
  @import url("https://fonts.googleapis.com/css?family=Dekko|Lato:900|Rock+Salt");
	#container {
		display: flex;
  	align-items: center;
  	justify-content: center;
		height: 100%;
	}
	textarea {
		display:block;
		margin: 20px auto;
		width: 400px;
		height: 200px;
        border: 2px solid black;
        background: #b0ff98;
        padding-left: 20px;
        padding-top: 20px;
        font-family: "Dekko", cursive;
        font-size: larger;

}
	.child {
		text-align: center;
	}
	.result {
		color: yellow;
		font-size: 2rem;
		font-weight: bold;
        font-family: "Dekko", cursive;

	}
</style>