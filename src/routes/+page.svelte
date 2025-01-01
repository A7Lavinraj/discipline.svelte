<script lang="ts">
	import { convertDayInWord, convertMonthInWord } from '$lib/date';
	const date = new Date();
</script>

<h2>{convertDayInWord(date.getDay())}</h2>
<p>{date.getDate()}&nbsp;{convertMonthInWord(date.getMonth())}&nbsp;{date.getFullYear()}</p>
