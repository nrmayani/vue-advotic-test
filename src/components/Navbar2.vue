<template>
  <div class="vertical-menu">
        <router-link class="nav-link" style="text-align-last: center;" to="/"><b-icon style="color: #5d5858; " icon="justify"></b-icon></router-link>
        <router-link class="nav-link" style="text-align-last: center;" to="/Dashboard"
          ><img class="dashboardIcon" src="../assets/img/dashboard-icon.png"
        /></router-link>
  </div>
</template>

<script>
export default {
  name: "Navbar2",
};
</script>

<style>
.vertical-menu {
  /* top: 64px;
  left: 0px;
  width: 72px;
  height: 859px; */
  top: 64px;
    left: 0px;
    width: 72px;
    height: 859px;
  /* background: #ffffff 0% 0% no-repeat padding-box; */
  border: 0.5px solid #d2d2d2;
  opacity: 1;
}

.vertical-menu a {
  color: black; /* Black text color */
  display: block; 
  padding: 12px; /* Add some padding */
  text-decoration: none; /* Remove underline from links */
}

.vertical-menu a:hover {
  background-color: #ccc; /* Dark grey background on mouse-over */
}

.vertical-menu a.active {
  background-color: #04aa6d; /* Add a green color to the "active/current" link */
  color: white;
}

.dashboardIcon {
  width: 25px;
  height: 25px;
  /* background: transparent url('img/Dashboard icon.png') 0% 0% no-repeat padding-box; */
  opacity: 1;
}
.active {
  background: chartreuse;
}

/* .nav-link {
    color: #C5C5C5;
} */
</style>
