<template>
  <div class="app">
    <AppHeader fixed>
      <SidebarToggler class="d-lg-none" display="md" mobile />
      <b-link class="navbar-brand" to="#">
        <img class="navbar-brand-full" src="http://story.monir.media/images/monirlogo.png" width="89" height="25" alt="Monir">
        <img class="navbar-brand-minimized" src="http://story.monir.media/images/monirlogosmall.png" width="30" height="30" alt="Monir">
      </b-link>
      <SidebarToggler class="d-md-down-none" display="lg" />
      <!--<b-navbar-nav class="d-md-down-none">-->
        <!--<b-nav-item class="px-3">Dashboard</b-nav-item>-->
        <!--<b-nav-item class="px-3">Users</b-nav-item>-->
        <!--<b-nav-item class="px-3">Settings</b-nav-item>-->
      <!--</b-navbar-nav>-->
      <b-navbar-nav class="ml-auto">
        <b-nav-item class="d-md-down-none">
            <i class="icon-magnifier icons font-2xl d-block mt-4" style="float: left; margin: 15px"></i>
            <p style="float: left; margin-right: 35px;margin-top: 25px;">Search...</p>
        </b-nav-item>
        <b-nav-item class="d-md-down-none" style="padding-right: 30px">
          <i class="cui-bell icons font-2xl d-block mt-4"style="float: left; margin: 15px"></i>
        </b-nav-item>

        <!--<b-nav-item class="d-md-down-none">-->
          <!--<i class="icon-list"></i>-->
        <!--</b-nav-item>-->
        <!--<b-nav-item class="d-md-down-none">-->
          <!--<i class="icon-location-pin"></i>-->
        <!--</b-nav-item>-->

      </b-navbar-nav>
      <!--<AsideToggler class="d-none d-lg-block" />-->
      <!--<AsideToggler class="d-lg-none" mobile />-->
    </AppHeader>
    <div class="app-body">
      <AppSidebar fixed>
        <SidebarHeader/>
        <SidebarForm/>
        <SidebarNav :navItems="nav"></SidebarNav>
        <SidebarFooter/>
        <SidebarMinimizer/>
      </AppSidebar>
      <main class="main">
        <div class="container-fluid">
          <router-view></router-view>
        </div>
      </main>
      <AppAside fixed>
        <!--aside-->
        <DafaultAside/>
      </AppAside>
    </div>
  </div>
</template>

<script>
import nav from '../_nav'
import { Header as AppHeader, SidebarToggler, Sidebar as AppSidebar, SidebarFooter, SidebarForm, SidebarHeader, SidebarMinimizer, SidebarNav, Aside as AppAside, AsideToggler, Footer as TheFooter, Breadcrumb } from '@coreui/vue'
import DafaultAside from './DafaultAside'
import DefaultHeaderDropdownAccnt from './DefaultHeaderDropdownAccnt'

export default {
  name: 'full',
  components: {
    AsideToggler,
    AppHeader,
    AppSidebar,
    AppAside,
    TheFooter,
    Breadcrumb,
    DafaultAside,
    DefaultHeaderDropdownAccnt,
    SidebarForm,
    SidebarFooter,
    SidebarToggler,
    SidebarHeader,
    SidebarNav,
    SidebarMinimizer
  },
  data () {
    return {
      nav: nav.items
    }
  },
  computed: {
    name () {
      return this.$route.name
    },
    list () {
      return this.$route.matched
    }
  }
}
</script>
