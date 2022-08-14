<template>
  <div class="fixed bg-white w-full h-14 p-3 z-10 flex">
  	<BaseTooltip text="Back" right>
  		<button class="p-2 focus:outline-none">
  			<BaseIcon name="arrowLeft" class="w-5 h-5" />
  		</button>
  	</BaseTooltip>
  	<Search />
  	<BaseTooltip text="Search with your voice" left>
  		<button class="p-2 focus:outline-none">
  			<BaseIcon name="microphone" class="w-5 h-5" />
  		</button>
  	</BaseTooltip>
  </div>
</template>

<script>
import BaseTooltip from './BaseTooltip.vue';
import BaseIcon from './BaseIcon.vue';
import Search from './Search.vue';

export default {
    components: { 
    	BaseTooltip, 
    	BaseIcon, 
    	Search 
    }
}
</script>