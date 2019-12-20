<template>

    <b-navbar id='navBar' type='dark' style="margin-bottom: 20px">
    <b-navbar-nav>
      <b-navbar-brand href="#" style="font-size: 2rem; letter-spacing: 3px"><b>Everybody Learns</b><img src="earth.png" alt="earth" height="50" style="padding-left: 20px"></b-navbar-brand>

      
    </b-navbar-nav>

    
    <b-navbar-nav class="ml-auto">
        <!-- Navbar dropdowns -->
      <b-nav-item-dropdown text="Lang" right>
        <b-dropdown-item href="#">EN</b-dropdown-item>
        <b-dropdown-item href="#">ES</b-dropdown-item>
        <b-dropdown-item href="#">RU</b-dropdown-item>
        <b-dropdown-item href="#">FA</b-dropdown-item>
      </b-nav-item-dropdown>

      <b-nav-item-dropdown text="User" right>
        <b-dropdown-item href="#">Account</b-dropdown-item>
        <b-dropdown-item href="#">Settings</b-dropdown-item>
      </b-nav-item-dropdown>
    </b-navbar-nav>
  </b-navbar>

</template>






<script>
export default {
    
}
</script>






<style scoped>
    #navBar {
        background-color: #0f1036;
        color: white;
    };

    #appName {
        font-size: 4rem;
        letter-spacing: 3px;
    };


</style>