<svelte:head>
	<link rel="stylesheet" href="/styles/jogar.css">
</svelte:head>

<script>

	import VoltarMenu from './VoltarMenu.svelte';
	import Button from './Button.svelte';

	const randomWordLetterCounter = function (wordReference) {
		let letterCount = 0;
			for(let stringIndex = 0; stringIndex < wordReference.length; stringIndex += 1) {
				letterCount += 1;
			
			};	return letterCount;
	};

	const wordsArray = new Array(["Cama", "É sobre Dormir"], ["Avião", "É um tipo de Transporte"], ["Mouse", "Integra o Computador"], ["Piano", "É um Instrumento Musical"],
								 ["Sorvete", "Um tipo de Comida Gelada"], ["Fogão", "É um Eletrodoméstico Comum"], ["Pão", "Comida Antiga, bem Antiga"], ["Arroz", "É um Gão Comum"],
								 ["Teclado", "Acessório de Computador"], ["Vento", "É uma Força Natural"], ["Reflexo", "Vemos no Espelho"], ["Elétron", "Faz parte do Átomo"]);

	const getRandomWordsOf = function (wordsArray, getWhat) {
		const previousAdress = (Math.floor(Math.random() * wordsArray.length));
			const preAssignment = {"Word" : 0, "Hint" : 1};
				return (getWhat === "Word" || getWhat === "word" || getWhat === "Hint" || getWhat === "hint") ? ((getWhat === "Word" || getWhat === "word") ? wordsArray[previousAdress][preAssignment.Word] : wordsArray[previousAdress][preAssignment.Hint]) : "Invalid Assignment";

	};
	const loadRandomHint = function () {
		document.getElementById('randomHint').innerText = getRandomWordsOf(wordsArray, "hint");
			return;
	};

    const wordsFrames = function (wordsLettersAmount) {
		for(let framesNumber = 0; framesNumber < wordsLettersAmount; framesNumber += 1) {
            
		};
	};
	export {randomWordLetterCounter, wordsArray, getRandomWordsOf, loadRandomHint, wordsFrames} from './Jogar.svelte';

</script>
	<body on:load={loadRandomHint()}>
		<div id="randomHint" class="hint"></div>
		<div id="imgforca"></div>
		<div id="hiddenWord">
		</div>
		<br>
		<br>
		<br>
		<div id="teclas">
		<div class="botao">	
		<Button on:click={'A'}>A</Button>
		<Button on:click={'B'}>B</Button>
		<Button on:click={'C'}>C</Button>
		<Button on:click={'D'}>D</Button>
		<Button on:click={'E'}>E</Button>
		<Button on:click={'F'}>F</Button>
		<Button on:click={'G'}>G</Button>
		<Button on:click={'H'}>H</Button>
		<Button on:click={'I'}>I</Button>
		<Button on:click={'J'}>J</Button>
		<Button on:click={'K'}>K</Button>
		<Button on:click={'L'}>L</Button>
		<Button on:click={'M'}>M</Button>
		</div><div class="botao">
		<Button on:click={'N'}>N</Button>
		<Button on:click={'O'}>O</Button>
		<Button on:click={'P'}>P</Button>
		<Button on:click={'Q'}>Q</Button>
		<Button on:click={'R'}>R</Button>
		<Button on:click={'S'}>S</Button>
		<Button on:click={'T'}>T</Button>
		<Button on:click={'U'}>U</Button>
		<Button on:click={'W'}>W</Button>
		<Button on:click={'X'}>X</Button>
		<Button on:click={'Y'}>Y</Button>
		<Button on:click={'Z'}>Z</Button>
		</div>
		</div><VoltarMenu/>
	</body>