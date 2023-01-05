<script>
	let name = '';
	let clicks = 0;
	let Yndlingsfilm = ''
	let showing = false
</script>

<main>
	<div>
		<h1>Vær hilset {name}!  <br>Håber du har en god dag </h1>
	
		<input bind:value={name} placeholder="skriv dit navn!">
		<p>
			Den bedste film i verden er <em>{Yndlingsfilm}</em>
		</p>
		<input bind:value={Yndlingsfilm} placeholder="bedst film">
		<button id="show" on:click={ () => showing ? showing = false: showing = true}>
		{#if showing == true}
			  Beklager
	  {/if}
		{#if showing == false}
			  Surprise
	  {/if}
		</button>
	</div>
</main>
{#if showing}
	<div id="background"></div>
{/if} 

<style>
	:global(body){overflow: hidden; margin: 0; padding: 0; font-size: 1.3rem;;
	
	
				}
	h1{
		font-weight: 500;
		color: black;

	}
	div{
		width: 100vw;
		height: 50vh;
		display: grid;
		place-items: center;
		z-index: 2;
	}
	main{
		display: grid;
		place-items: center;
		background: linear-gradient(to left bottom, #051937, #004d7a, #008793, #00bf72, #a8eb12);
    	width: 100vw;
    	height: 100vh;
    	overflow: hidden;
		z-index: -2;
	}



	#show{
		width: 150 px;
	}
		input{
		width: 200px;
		background-color: lightgray;
	}


#background{
	background-image: url("https://media.tenor.com/_4YgA77ExHEAAAAd/rick-roll.gif%22");
	position: fixed;
	widows: 100vw;
	height: 100vh;
	z-index: 0;
	left: 0;
	top: 0;
	background-repeat: no-repeat;
	background-size: cover;
}

	button{
		width: 110px;
		color: white;
		background-color: grey;
		border: grey;
		position:relative;

	}
		button:hover{
			background-image: linear-gradient(90deg, #00C0FF 0%, #FFCF00 49%, #FC4F4F 80%, #00C0FF 100%);
   			animation:slidebg 5s linear infinite;

	}

	@keyframes slidebg {
  to {
    background-position:20vw;
  }
}

.follow{
  margin-top: 40px;
}

.follow a{
  color: black;
  padding: 8px 16px;
  text-decoration: none;
}

</style>