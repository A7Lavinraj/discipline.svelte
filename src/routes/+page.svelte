<script lang="ts">
	import { convertDayInWord, convertMonthInWord } from '$lib/date';
	const date = new Date();
	const TASKS = ['LeetCode', 'GeeksForGeeks', 'Codechef', 'Codeforces'];
</script>

<span class="text-4xl">{convertDayInWord(date.getDay())}</span>
<p class="mt-2 text-base text-neutral-600">
	{date.getDate()}&nbsp;{convertMonthInWord(date.getMonth())}&nbsp;{date.getFullYear()}
</p>

<h2 class="mt-5 text-lg font-semibold">&#35;Mendatory tasks</h2>
<form>
	{#each TASKS as task}
		<div class="mt-2 max-w-full border border-neutral-800 px-4 py-4">
			<input type="checkbox" id={task} class="peer" />
			<label
				for={task}
				class="ml-5 transition peer-checked:text-neutral-600 peer-checked:line-through"
				>{task}</label
			>
		</div>
	{/each}
	<textarea
		name="extra-activities"
		id="extra-activities"
		class="mt-4 min-h-32 w-full resize-none rounded"
	></textarea>
	<button type="submit" class="mt-4 w-full rounded bg-zinc-700 px-2 py-2 font-semibold"
		>update</button
	>
</form>
