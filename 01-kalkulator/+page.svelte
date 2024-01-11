<script>
	let displayTekst = '';
	const leggTilDisplay = (knapp) => {
		displayTekst += knapp;
	};

	const slettAlt = () => {
		displayTekst = '';
	};
	const regnUt = () => {
		try {
			displayTekst = eval(displayTekst);
		} catch (error) {
			displayTekst = 'Error';
		}
		displayTekst = displayTekst.toString();
		if (displayTekst.length >= 14) {
			displayTekst = displayTekst.slice(0, 1);
		}
	};
</script>

<div id="kalkulator">
	<div id="display">
		{displayTekst.replace('*', '×').replace('/', '÷').replace('.', ',')}
	</div>
	<div id="tastatur">
		<button
			on:click={() => {
				leggTilDisplay('7');
			}}>7</button
		>
		<button
			on:click={() => {
				leggTilDisplay('8');
			}}>8</button
		>
		<button
			on:click={() => {
				leggTilDisplay('9');
			}}>9</button
		>
		<button
			on:click={() => {
				leggTilDisplay('/');
			}}>÷</button
		>
		<button
			on:click={() => {
				leggTilDisplay('4');
			}}>4</button
		>
		<button
			on:click={() => {
				leggTilDisplay('5');
			}}>5</button
		>
		<button
			on:click={() => {
				leggTilDisplay('6');
			}}>6</button
		>
		<button
			on:click={() => {
				leggTilDisplay('*');
			}}>×</button
		>
		<button
			on:click={() => {
				leggTilDisplay('1');
			}}>1</button
		>
		<button
			on:click={() => {
				leggTilDisplay('2');
			}}>2</button
		>
		<button
			on:click={() => {
				leggTilDisplay('3');
			}}>3</button
		>
		<button
			on:click={() => {
				leggTilDisplay('-');
			}}>–</button
		>
		<button
			on:click={() => {
				leggTilDisplay('0');
			}}>0</button
		>
		<button
			on:click={() => {
				leggTilDisplay('.');
			}}>,</button
		>
		<button
			on:click={() => {
				regnUt();
			}}>=</button
		>
		<button
			on:click={() => {
				leggTilDisplay('+');
			}}>+</button
		>
		<button
			on:click={() => {
				slettAlt();
			}}>C</button
		>
	</div>
</div>

<style>
	div#kalkulator {
		background-color: rgb(19, 19, 19);
		width: min(80vw, 60vh);
		aspect-ratio: 1/1.4;
		font-size: clamp(0.5rem, 10vw, 5rem);
		font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
		color: white;
		border-radius: 1rem;
	}
	div#display {
		display: flex;
		align-items: center;
		justify-content: flex-end;
		border-top-left-radius: 1rem;
		border-top-right-radius: 1rem;
		background-color: rgb(62, 62, 62);
		text-align: right;
		/* font-size: 250%; */
		height: 20%;
		padding-right: 2rem;
		overflow: hidden;
	}
	div#tastatur {
		display: grid;
		grid-template-columns: repeat(4, 1fr);
		padding: 1rem;
	}

	button {
		font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
		font-size: clamp(0.5rem, 8vw, 3rem);
		color: white;
		margin: 5%;
		border-radius: 50%;
		aspect-ratio: 1;
		border: none;
		padding: 0em;
		display: flex;
		justify-content: center;
		align-items: center;
		background-color: rgb(100, 100, 100);
		cursor: pointer;
		user-select: none;
		animation: all 0.3s ease-out;
	}

	button:hover {
		background-color: rgb(130, 130, 130);
	}

	button:active {
		transform: scale(0.95);
	}

	button:nth-child(4n),
	button:nth-child(15),
	button:nth-child(17) {
		background-color: rgb(229, 133, 43);
	}
	button:nth-child(4n):hover,
	button:nth-child(15):hover,
	button:nth-child(17):hover {
		background-color: rgb(235, 160, 89);
	}
</style>
