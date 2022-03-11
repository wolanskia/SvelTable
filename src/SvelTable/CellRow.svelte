<script>
	import Cell from './Cell.svelte';
	export let rowData = {};
	export let onRowClick = (e, row, index) => {};
	export let onCellClick = (e, { }) => {};
</script>

<div class="SvelTableRow">
	{#each Object.values(rowData) as keyVal, j}
		<div on:click={(e) => onRowClick(e, rowData, j)}>
			<Cell displayText={keyVal} colID={j} {onCellClick} />
		</div>
	{/each}
</div>

<style>
	.SvelTableRow {
		display: flex;
		flex-direction: row;
	}
</style>
