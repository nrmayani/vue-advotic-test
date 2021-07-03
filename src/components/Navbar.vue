<template>
  <nav class="navbar navbar-expand-lg">
    <div class="container-fluid">
      <div class="collapse navbar-collapse" id="navbarSupportedContent">
        <ul class="navbar-nav me-auto mb-2 mb-lg-0">
          <img src="../assets/img/advotics-logo.png" />
        </ul>
        <ul class="navbar-nav ml-auto">
          <div>
            <p class="username">Username</p>
            <p class="companyName">Company Name</p>
          </div>
          <img class="profileIcon" src="../assets/img/profile.png" />
          <img class="logout" src="../assets/img/logout.png" />
        </ul>
      </div>
    </div>
  </nav>
</template>

<script>
export default {
  name: "Navbar",
};
</script>

<style scope>
nav {
  top: 0px;
  left: 0px;
  height: 64px;
  background: #ffffff 0% 0% no-repeat padding-box;
  box-shadow: 0px 3px 6px #00000029;
  opacity: 1;
}

.username {
  margin-top: 16px;
  margin-bottom: 0px;
  text-align: center;
  /* font: normal normal 600 14px/19px ; */
  /* font-family:; */
  letter-spacing: 0px;
  color: #727272;
  opacity: 1;
  font-family: sans-serif;
  font-style: normal;
  font-size: 14px;
  line-height: 19px;
}

.companyName {
  text-align: center;
  letter-spacing: 0px;
  color: #727272;
  opacity: 1;
  font-family: sans-serif;
  font-style: normal;
  font-size: 10px;
  line-height: 14px;
}

.profileIcon {
  align-self: center;
  height: 32px;
  opacity: 1;
  margin-left: 15px;
}

.logout {
  align-self: center;
  opacity: 1;
  margin-left: 15px;
  width: 15px;
  height: 15px;
}
</style>
