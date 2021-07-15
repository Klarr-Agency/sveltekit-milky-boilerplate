<script lang="typescript">
    export let iconName;
    export let width = "24px";
    export let height = "24px";
    let icons = [
        {
            color: "#fff",
            box: 24,
            iconName: "home",
            svg: `<path d="M3 9l9-7 9 7v11a2 2 0 0 1-2 2H5a2 2 0 0 1-2-2z"></path><polyline points="9 22 9 12 15 12 15 22"></polyline>`
        },
        {
            color: "#fff",
            box: 24,
            iconName: "products",
            svg: `<line x1="16.5" y1="9.4" x2="7.5" y2="4.21"></line><path d="M21 16V8a2 2 0 0 0-1-1.73l-7-4a2 2 0 0 0-2 0l-7 4A2 2 0 0 0 3 8v8a2 2 0 0 0 1 1.73l7 4a2 2 0 0 0 2 0l7-4A2 2 0 0 0 21 16z"></path><polyline points="3.27 6.96 12 12.01 20.73 6.96"></polyline><line x1="12" y1="22.08" x2="12" y2="12"></line>`
        },
        {
            color: "#fff",
            box: 24,
            iconName: "blog",
            svg: `<path d="M4 19.5A2.5 2.5 0 0 1 6.5 17H20"></path><path d="M6.5 2H20v20H6.5A2.5 2.5 0 0 1 4 19.5v-15A2.5 2.5 0 0 1 6.5 2z"></path>`
        }
    ];
    let displayIcon = icons.find((e) => e.iconName === iconName);
</script>
<svg
  class={$$props.class}
  {width}
  {height}
  viewBox="0 0 {displayIcon.box} {displayIcon.box}"
  fill="none" stroke="{displayIcon.color}" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">{@html displayIcon.svg}</svg>