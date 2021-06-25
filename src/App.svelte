<script>
	
	let quiz = [{q:"What's your favorite hobby?",a:["Video Games", "Sleeping", "Reading","Roasting Marshmellows", "Singing"]},{q:"What's your favorite color?",a:["Yellow", "Black", "Brown","Orange", "pink"]},{q:"Where would you like to live?",a:["Mountains", "Town", "Fields","Desert", "Forrests"]},{q:"What's your favorite thing to do when you're bored?",a:["Play outside", "Sleep", "Reading","Flying in the air", "Practicing Singing"]},{q:"What's your favorite music?",a:["Rock and Roll!", "Lullibys", "Hip-Hop","Beatboxing", "Me!"]}];
	let answers=[];
	let message = "";
	let picture = "";
	function setAnswers(question,answer){
		answers[question] = answer;
		console.log(answers);
	}
	
	function findAnswer(){
		let total = answers.reduce((a, b) => a + b, 0);
		if(total<3){
			message="You're Pikachu!!!"
			picture="https://cdn.europosters.eu/image/1300/posters/pokemon-pikachu-neon-i71936.jpg"
		}
		else if(total<7){
			message ="You're Snorlax!!!"
			picture="https://staticg.sportskeeda.com/editor/2021/06/2737a-16233453234465-800.jpg"
		}
		else if(total<12){
			message ="You're Evee!!!"
			picture="https://www.kindpng.com/picc/m/120-1204340_transparent-evee-png-chibi-pokemon-eevee-png-download.png"
		}
		else if(total<17){
			message ="You're Charzard!!!"
			picture = "https://cdn2.bulbagarden.net/upload/thumb/b/bd/Leon_Charizard.png/250px-Leon_Charizard.png"
		}
		else{
			message ="You're Jigglypuff!!!"
			picture="https://pbs.twimg.com/profile_images/1237769626148392961/aayCh0EU_400x400.jpg"
		}
	}
	
</script>



{#each quiz as question,i}
	{question.q}
	<br>
	<br>

	

	
		{#each question.a as answer, k}
		<label for={answer}>{answer}</label>
  	<input type="radio" id={answer} name={i} value={k} on:click = {()=>setAnswers(i,k)}>

 
			
			
		{/each}
	
<br>
<br>
<br>
{/each}


<p>
	{message}
</p>
<img src={picture} >
<button on:click={findAnswer}>
	FIND OUT WHAT POKEMON YOU ARE!!!!
</button>
<br>
<br>
<button on:click={()=>window.location.reload()}>
	Click to take the test again!!!
</button>

<style>
	




	

</style>