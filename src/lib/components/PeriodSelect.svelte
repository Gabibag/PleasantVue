<script>
	import { session } from '$lib/stores/session.js'
	export let period
</script>

<select bind:value={period}>
	{#each ($session?.gradebook?.ReportingPeriods?.[0]?.ReportPeriod || []) as period, index}
		<option value={index}>{period.$.GradePeriod}</option>
	{/each}
</select>

<style lang="scss">
	select {
		@include box;
		padding: $spacing-small;
		width: fit-content;
		margin-left: auto;
		&:hover {
			cursor: pointer;
			background: var(--bg-color-2-5);
		}
	}
</style>
