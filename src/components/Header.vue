<template>
	<header class="flex justify-between fixed z-30 w-full bg-white">
    <div class="flex lg:w-1/4">
      <div class="flex items-center xl:w-64 xl:bg-white pl-4">
        <button @click="$emit('toggleSidebar')"
                class="mr-3 sm:ml-2 sm:mr-6 focus:outline-none"
        >
          <BaseIcon name="menu" />
        </button>
        <LogoMain />
      </div>
    </div>
    <SearchMobile />
    <div class="hidden sm:flex items-center justify-end p-2.5 pl-8 md:pl-12 md:px-8 flex-1 lg:px-0 lg:w-1/2 max-w-screen-md">
      <Search />
      <BaseTooltip text="Search with your voice">
        <button class="p-2 focus:outline-none">
          <BaseIcon name="microphone" class="w-5 h-5" />
        </button>
      </BaseTooltip>
    </div>
    <div class="flex items-center justify-end lg:w-1/4 space-x-3 p-2 sm:px-4">
      <BaseTooltip text="Search with your voice">
        <button class="sm:hidden p-2 focus:outline-none">
          <BaseIcon name="microphone" class="w-5 h-5" />
        </button>
      </BaseTooltip>
      <BaseTooltip text="Search">
        <button class="sm:hidden p-2 focus:outline-none">
          <BaseIcon name="search" class="w-5 h-5" />
        </button>
      </BaseTooltip>
      <button class="relative group p-2 focus:outline-none">
        <BaseIcon name="viewGrid" class="w-5 h-5" />
        <DropdownApps />
      </button>
      <button class="relative group p-2 focus:outline-none">
        <BaseIcon name="dotsVertical" class="w-5 h-5" />
        <DropdownSettings />
      </button>
      <DropdownApps />
      <DropdownSettings />
      <LoginButton />
    </div>
  </header>
</template>

<script>
import LogoMain from './LogoMain.vue'
import BaseIcon from './BaseIcon.vue'
import BaseTooltip from './BaseTooltip.vue'
import LoginButton from './LoginButton.vue'
import Search from './Search.vue'
import SearchMobile from './SearchMobile.vue'
import DropdownApps from './DropdownApps.vue'
import DropdownSettings from './DropdownSettings.vue'

export default {
	components: {
    LogoMain,
    BaseIcon,
    BaseTooltip,
    LoginButton,
    Search,
    SearchMobile,
    DropdownApps,
    DropdownSettings,
    Search
},
  emits: {
    toggleSidebar: null
  }
}
</script>