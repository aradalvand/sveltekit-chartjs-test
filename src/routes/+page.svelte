<script>
	import { Chart } from 'chart.js/auto';
	import { onMount } from 'svelte';
	let canvas;
	onMount(() => {
		console.log('canvas:', canvas);
		const hey = [
			{ year: 2010, count: 10 },
			{ year: 2011, count: 20 },
			{ year: 2012, count: 15 },
			{ year: 2013, count: 25 },
			{ year: 2014, count: 22 },
			{ year: 2015, count: 30 },
			{ year: 2016, count: 28 },
		];
		new Chart(canvas, {
			type: 'bar',
			data: {
				labels: hey.map(row => row.year),
				datasets: [
					{
						label: 'Acquisitions by year',
						data: hey.map(row => row.count),
					},
				],
			},
		});
		console.log('chart created');
	});
</script>

<canvas bind:this={canvas} />
