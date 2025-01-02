<script lang="ts">
	import { enhance } from '$app/forms';
	import { convertDayInWord, convertMonthInWord } from '$lib/date';

	const date = new Date();
	const TASKS = ['leetcode', 'geeksforgeeks', 'codechef', 'codeforces', 'github'];
</script>

<span class="text-4xl">{convertDayInWord(date.getDay())}</span>

<p class="mt-2 text-base text-neutral-600">
	{date.getDate()}&nbsp;{convertMonthInWord(date.getMonth())}&nbsp;{date.getFullYear()}
</p>

<form method="POST" action="?/update" use:enhance>
	<h2 class="mt-5 text-lg font-semibold">&#35;Mendatory tasks</h2>

	{#each TASKS as task}
		<div class="my-2 flex w-full">
			<input type="checkbox" id={task} class="peer" hidden name={task} />
			<label
				for={task}
				class="h-full flex-1 rounded border border-neutral-800 p-4 peer-checked:border-emerald-500 peer-checked:bg-emerald-950/20"
				>{task}</label
			>
		</div>
	{/each}

	<h2 class="mt-5 text-lg font-semibold">&#35;Extra activities</h2>

	<textarea
		name="extra-activities"
		id="extra-activities"
		class="mt-4 min-h-32 w-full resize-none rounded"
	></textarea>

	<button type="submit" class="mt-4 w-full rounded bg-zinc-700 px-2 py-2 font-semibold"
		>update</button
	>
</form>
