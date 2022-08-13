<template>
	<div class="flex w-full h-full mr-2">
		<SearchInput />
		<SearchButton />
	</div>
</template>

<script>
import SearchInput from './SearchInput.vue'
import SearchButton from './SearchButton.vue'

export default {
	components: {
		SearchInput,
		SearchButton
	}
}
</script>