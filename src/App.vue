<template>
  <Header @toggle-sidebar="toggleSidebar" />
  <SidebarSmall :is-open="sidebarState === 'compact'" />
  <Sidebar :is-open="sidebarState === 'normal'" />
  <SidebarMobile :is-open="isMobileSidebarOpen"
                 @close="closeMobileSidebar"
  />
  <Categories :is-sidebar-open="sidebarState === 'normal'" />
  <Videos :is-sidebar-open="sidebarState === 'normal'" />
</template>

<script>
import Header from './components/Header.vue'
import SidebarSmall from './components/SidebarSmall.vue'
import Sidebar from './components/Sidebar.vue'
import SidebarMobile from './components/SidebarMobile.vue'
import Categories from './components/Categories.vue'
import Videos from './components/Videos.vue'

export default {
  components: {
    Header,
    SidebarSmall,
    Sidebar,
    SidebarMobile,
    Categories,
    Videos
  },
  data () {
    return {
      isMobileSidebarOpen: false,
      sidebarState: null
    }
  },
  mounted () {
    if (window.innerWidth >= 768 && window.innerWidth < 1280) {
      this.sidebarState = 'compact'
    }
    if (window.innerWidth >= 1280) {
      this.sidebarState = 'normal'
    }
  },
  methods: {
    toggleSidebar () {
      if (window.innerWidth >= 1280) {
        this.sidebarState = this.sidebarState === 'normal' ? 'compact' : 'normal' 
      } else {
        this.openMobileSidebar()
      }
    },
    openMobileSidebar () {
      this.isMobileSidebarOpen = true
    },
    closeMobileSidebar () {
      this.isMobileSidebarOpen = false
    },
  }
}
</script>