<template>
  <nav
    class="navbar  navbar-transparent    navbar-expand-lg "
    color-on-scroll="100"
    id="sectionsNav"
  >
    <div class="container">
      <div class="navbar-translate">
        <a class="navbar-brand" href="#" target="_blank">Rule of thumb</a>
        <button
          class="navbar-toggler"
          type="button"
          data-toggle="collapse"
          aria-expanded="false"
          aria-label="Toggle navigation"
        >
          <span class="navbar-toggler-icon"></span>
          <span class="navbar-toggler-icon"></span>
          <span class="navbar-toggler-icon"></span>
        </button>
      </div>

      <div class="collapse navbar-collapse">
        <ul class="navbar-nav ml-auto">
          <li class="dropdown nav-item">
            <a href="#" class=" nav-link">
              Past Trials
            </a>
          </li>
          <li class="nav-item">
            <a class="nav-link" href="javascript:void(0)">
              How it works
            </a>
          </li>
          <li class="dropdown nav-item">
            <a href="#" class=" nav-link">
              Log In / Sign Up
            </a>
          </li>

          <li class="nav-item">
            <a class="nav-link" href="search" target="_blank">
              <i class="fa fa-search"></i>
            </a>
          </li>
        </ul>
      </div>
    </div>
  </nav>
</template>
<script lang="ts">
import { Component, Prop, Vue } from "vue-property-decorator";
@Component
export default class Menu extends Vue {}
</script>
<style scoped lang="scss">
.h6,
h6 {
  font-size: 0.75rem !important;
  font-weight: 500;
  font-family: Roboto, Helvetica, Arial, sans-serif;
  line-height: 1.5em;
  text-transform: uppercase;
}

.name h6 {
  margin-top: 10px;
  margin-bottom: 10px;
}

.navbar {
  border: 0;
  border-radius: 3px;
  padding: 0.625rem 0;
  margin-bottom: 20px;
  color: #555;
  font-size: 32px;
  background-color: #fff !important;
  box-shadow: 0 4px 18px 0 rgba(0, 0, 0, 0.12),
    0 7px 10px -5px rgba(0, 0, 0, 0.15) !important;
  z-index: 1000 !important;
  transition: all 150ms ease 0s;
}

.navbar.navbar-transparent {
  z-index: 1030;
  background-color: transparent !important;
  box-shadow: none !important;
  padding-top: 25px;
  color: #fff;
}

.navbar .navbar-brand {
  position: relative;
  color: inherit;
  height: 50px;
  font-size: 32px;
  line-height: 30px;
  padding: 0.625rem 0;
  font-weight: 300;
  -webkit-font-smoothing: antialiased;
}

.navbar .navbar-nav .nav-item .nav-link:not(.btn) .material-icons {
  margin-top: -7px;
  top: 3px;
  position: relative;
  margin-right: 3px;
}

.navbar .navbar-nav .nav-item .nav-link .material-icons {
  font-size: 1.25rem;
  max-width: 24px;
  margin-top: -1.1em;
}

.navbar .navbar-nav .nav-item .nav-link .fa,
.navbar .navbar-nav .nav-item .nav-link .material-icons {
  font-size: 1.25rem;
  max-width: 24px;
  margin-top: 0px;
}

.navbar .navbar-nav .nav-item .nav-link {
  position: relative;
  color: inherit;
  padding: 0.9375rem;
  font-weight: 400;
  font-size: 16px;
  border-radius: 3px;
  line-height: 20px;
}

a .material-icons {
  vertical-align: middle;
}

.fixed-top {
  position: fixed;
  z-index: 1030;
  left: 0;
  right: 0;
}

.main {
  background: #fff;
  position: relative;
  z-index: 3;
}

.img-fluid,
.img-thumbnail {
  max-width: 100%;
  height: auto;
}

.title {
  margin-top: 30px;
  margin-bottom: 25px;
  min-height: 32px;
  color: #3c4858;
  font-weight: 700;
  font-family: "Lato", sans-serif;
}

.profile-page .profile-tabs {
  margin-top: 4.284rem;
}

.nav-pills,
.nav-tabs {
  border: 0;
  border-radius: 3px;
  padding: 0 15px;
}

.nav .nav-item {
  position: relative;
  margin: 0 2px;
}

.nav-pills.nav-pills-icons .nav-item .nav-link {
  border-radius: 4px;
}

.nav-pills .nav-item .nav-link.active {
  color: #fff;
  background-color: #9c27b0;
  box-shadow: 0 5px 20px 0 rgba(0, 0, 0, 0.2),
    0 13px 24px -11px rgba(156, 39, 176, 0.6);
}

.nav-pills .nav-item .nav-link {
  line-height: 24px;
  font-size: 32px;
  font-weight: 500;
  min-width: 100px;
  color: #555;
  transition: all 0.3s;
  border-radius: 30px;
  padding: 10px 15px;
  text-align: center;
}

.nav-pills .nav-item .nav-link:not(.active):hover {
  background-color: rgba(200, 200, 200, 0.2);
}

.nav-pills .nav-item i {
  display: block;
  font-size: 30px;
  padding: 15px 0;
}

.tab-space {
  padding: 20px 0 50px;
}

.profile-page .gallery {
  margin-top: 3.213rem;
  padding-bottom: 50px;
}

.profile-page .gallery img {
  width: 100%;
  margin-bottom: 2.142rem;
}

.profile-page .profile .name {
  margin-top: -80px;
}

img.rounded {
  border-radius: 6px !important;
}

.tab-content > .active {
  display: block;
}

/*buttons*/
.btn {
  position: relative;
  padding: 12px 30px;
  margin: 0.3125rem 1px;
  font-size: 0.75rem;
  font-weight: 400;
  line-height: 1.428571;
  text-decoration: none;
  text-transform: uppercase;
  letter-spacing: 0;
  border: 0;
  border-radius: 0.2rem;
  outline: 0;
  transition: box-shadow 0.2s cubic-bezier(0.4, 0, 1, 1),
    background-color 0.2s cubic-bezier(0.4, 0, 0.2, 1);
  will-change: box-shadow, transform;
}

.btn.btn-just-icon {
  font-size: 20px;
  height: 41px;
  min-width: 41px;
  width: 41px;
  padding: 0;
  overflow: hidden;
  position: relative;
  line-height: 41px;
}

.btn.btn-just-icon fa {
  margin-top: 0;
  position: absolute;
  width: 100%;
  transform: none;
  left: 0;
  top: 0;
  height: 100%;
  line-height: 41px;
  font-size: 20px;
}
.btn.btn-link {
  background-color: transparent;
  color: #999;
}

/* dropdown */

.dropdown-menu {
  position: absolute;
  top: 100%;
  left: 0;
  z-index: 1000;
  float: left;
  min-width: 11rem !important;
  margin: 0.125rem 0 0;
  font-size: 1rem;
  color: #212529;
  text-align: left;
  background-color: #fff;
  background-clip: padding-box;
  border-radius: 0.25rem;
  transition: transform 0.3s cubic-bezier(0.4, 0, 0.2, 1),
    opacity 0.2s cubic-bezier(0.4, 0, 0.2, 1);
}

.dropdown-menu.show {
  transition: transform 0.3s cubic-bezier(0.4, 0, 0.2, 1),
    opacity 0.2s cubic-bezier(0.4, 0, 0.2, 1);
}

.dropdown-menu .dropdown-item:focus,
.dropdown-menu .dropdown-item:hover,
.dropdown-menu a:active,
.dropdown-menu a:focus,
.dropdown-menu a:hover {
  box-shadow: 0 4px 20px 0 rgba(0, 0, 0, 0.14),
    0 7px 10px -5px rgba(156, 39, 176, 0.4);
  background-color: #9c27b0;
  color: #fff;
}
.show .dropdown-toggle:after {
  transform: rotate(180deg);
}

.dropdown-toggle:after {
  will-change: transform;
  transition: transform 0.15s linear;
}

.dropdown-menu .dropdown-item,
.dropdown-menu li > a {
  position: relative;
  width: auto;
  display: flex;
  flex-flow: nowrap;
  align-items: center;
  color: #333;
  font-weight: 400;
  text-decoration: none;
  font-size: 0.8125rem;
  border-radius: 0.125rem;
  margin: 0 0.3125rem;
  transition: all 0.15s linear;
  min-width: 7rem;
  padding: 0.625rem 1.25rem;
  min-height: 1rem !important;
  overflow: hidden;
  line-height: 1.428571;
  text-overflow: ellipsis;
  word-wrap: break-word;
}

.dropdown-menu.dropdown-with-icons .dropdown-item {
  padding: 0.75rem 1.25rem 0.75rem 0.75rem;
}

.dropdown-menu.dropdown-with-icons .dropdown-item .material-icons {
  vertical-align: middle;
  font-size: 24px;
  position: relative;
  margin-top: -4px;
  top: 1px;
  margin-right: 12px;
  opacity: 0.5;
}
</style>
