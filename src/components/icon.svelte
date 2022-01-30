<script lang="typescript">
	export let iconName;
	export let width = '24px';
	export let height = '24px';
	let icons = [
		{
			color: '#fff',
			box: 24,
			iconName: 'home',
			svg: `<path d="M3 9l9-7 9 7v11a2 2 0 0 1-2 2H5a2 2 0 0 1-2-2z"></path><polyline points="9 22 9 12 15 12 15 22"></polyline>`
		},
		{
			color: '#fff',
			box: 24,
			iconName: 'pie',
			svg: `<path d="M21.21 15.89A10 10 0 1 1 8 2.83"></path><path d="M22 12A10 10 0 0 0 12 2v10z"></path>`
		},
		{
			color: '#fff',
			box: 24,
			iconName: 'blog',
			svg: `<path d="M4 19.5A2.5 2.5 0 0 1 6.5 17H20"></path><path d="M6.5 2H20v20H6.5A2.5 2.5 0 0 1 4 19.5v-15A2.5 2.5 0 0 1 6.5 2z"></path>`
		},
		{
			color: '#fff',
			box: 24,
			iconName: 'preview',
			svg: `<path d="M1 12s4-8 11-8 11 8 11 8-4 8-11 8-11-8-11-8z"></path><circle cx="12" cy="12" r="3"></circle>`
		}
	];
	let displayIcon = icons.find((e) => e.iconName === iconName);
</script>

<svg
	class={$$props.class}
	{width}
	{height}
	viewBox="0 0 {displayIcon.box} {displayIcon.box}"
	fill="none"
	stroke={displayIcon.color}
	stroke-width="2"
	stroke-linecap="round"
	stroke-linejoin="round"
>
	{@html displayIcon.svg}
</svg>
