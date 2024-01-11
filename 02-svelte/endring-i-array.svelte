<script>
	let filmer = ['Ben Hur', 'Sharknado 2'];
	filmer.splice(0, 1);
	filmer.push('Sharknado 3');
	filmer.unshift('Sharknado');
	filmer[3] = 'Sharknado 5';
	filmer.splice(3, 0, 'Sharknado 4');
</script>
<ul>
{#each filmer as film}
<li>{film}</li>
    
{/each}
</ul>