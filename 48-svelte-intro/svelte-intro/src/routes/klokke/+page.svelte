<script>
	let date;

	function updateTime() {
		date = new Date().toLocaleTimeString('nb-NO');
	}
	setInterval(updateTime, 1000);
</script>

<h1>{date}</h1>
