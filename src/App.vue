<template>
  <div class="fixed w-full z-30">
    <Header @toggle-sidebar="toggleSidebar" />
    <Categories :is-sidebar-open="isSidebarOpen" />
  </div>
  <SidebarCompact v-if="isCompactSidebarOpen" />
  <Sidebar v-if="isSidebarOpen" />
  <SidebarMobile :is-open="isMobileSidebarOpen"
                 @close="closeMobileSidebar"
  />
  <Videos :is-sidebar-open="isSidebarOpen" />
</template>

<script>
import Header from './components/Header.vue'
import SidebarCompact from './components/SidebarCompact.vue'
import Sidebar from './components/Sidebar.vue'
import SidebarMobile from './components/SidebarMobile.vue'
import Categories from './components/Categories.vue'
import Videos from './components/Videos.vue'

export default {
  components: {
    Header,
    SidebarCompact,
    Sidebar,
    SidebarMobile,
    Categories,
    Videos
  },
  data () {
    return {
      isMobileSidebarOpen: false,
      isSidebarOpen: false,
      isCompactSidebarActive: false,
      isCompactSidebarOpen: false
    }
  },
  mounted () {
    this.onResize()

    window.addEventListener('resize', this.onResize)
  },
  methods: {
    onResize () {
      if (window.innerWidth < 768) {
        this.isCompactSidebarOpen = false
        this.isSidebarOpen = false
      } else if (window.innerWidth < 1280) {
        this.isCompactSidebarOpen = true
        this.isSidebarOpen = false
      } else {
        this.isCompactSidebarOpen = this.isCompactSidebarActive
        this.isSidebarOpen = !this.isCompactSidebarActive
        this.isMobileSidebarOpen = false
      }
    },
    
    toggleSidebar () {
      if (window.innerWidth >= 1280) {
        this.isCompactSidebarActive = !this.isCompactSidebarActive

        this.onResize() 
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