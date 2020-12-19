<template>
  <div class="wrapper">
    <side-bar>
      <template slot="links">
        <sidebar-link to="/Home" name="หน้าแรก" icon="ti-home" />
        <sidebar-link to="/stats" name="พนักงาน" icon="ti-user" />
        <li class="nav-item">
          <!--<drop-down
            class="nav-item"
            title="พนักงาน"
            title-classes="nav-link"
            icon="ti-user"
          >
            <sidebar-link to="/stats" name="พนักงาน" icon="ti-user" /> -->
          <a href="#" class="nav-link"><i class="ti-user"></i>พนักงาน</a>
          <div class="smenu">
            <a href="#">การจัดการพนักงาน</a>
            <a href="#">2post</a>
          </div>
          <!-- </drop-down> -->
        </li>
        <sidebar-link
          to="/table-list"
          name="ตารางเวลางาน"
          icon="ti-view-list-alt"
        />
        <sidebar-link to="/typography" name="วันลา" icon="ti-calendar" />
        <sidebar-link to="/icons" name="เงินเดือน" icon="ti-money" />
        <sidebar-link to="/maps" name="จุดลงเวลา" icon="ti-location-pin" />
        <sidebar-link to="/notifications" name="บริษัท" icon="ti-briefcase" />
        <sidebar-link to="/Setting" name="ตั้งค่า" icon="ti-settings" />
      </template>
      <mobile-menu>
        <li class="nav-item">
          <a class="nav-link">
            <i class="ti-panel"></i>
            <p>Stats</p>
          </a>
        </li>
        <drop-down
          class="nav-item"
          title="5 Notifications"
          title-classes="nav-link"
          icon="ti-bell"
        >
          <a class="dropdown-item">Notification 1</a>
          <a class="dropdown-item">Notification 2</a>
          <a class="dropdown-item">Notification 3</a>
          <a class="dropdown-item">Notification 4</a>
          <a class="dropdown-item">Another notification</a>
        </drop-down>
        <li class="nav-item">
          <a class="nav-link">
            <i class="ti-settings"></i>
            <p>Settings</p>
          </a>
        </li>
        <li class="divider"></li>
      </mobile-menu>
    </side-bar>
    <div class="main-panel">
      <top-navbar></top-navbar>

      <dashboard-content @click.native="toggleSidebar"> </dashboard-content>

      <content-footer></content-footer>
    </div>
  </div>
</template>
<style lang="scss">
</style>
<script>
import TopNavbar from "./TopNavbar.vue";
import ContentFooter from "./ContentFooter.vue";
import DashboardContent from "./Content.vue";
import MobileMenu from "./MobileMenu";
import SidebarLink from "../../components/SidebarPlugin/SidebarLink.vue";
export default {
  components: {
    TopNavbar,
    ContentFooter,
    DashboardContent,
    MobileMenu,
    SidebarLink,
  },
  methods: {
    toggleSidebar() {
      if (this.$sidebar.showSidebar) {
        this.$sidebar.displaySidebar(false);
      }
    },
  },
};
</script>
