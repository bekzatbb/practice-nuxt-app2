<template>
	<input class="border border-gray-300 w-full px-3 shadow-inner rounded-bl-sm rounded-tl-sm focus:border-blue-700 focus:outline-none" placeholder="Search" type="text">
</template>

<script>
export default {
	mounted () {
		if (window.innerWidth < 640) {
			this.$el.focus()
		}
	}
}
</script>