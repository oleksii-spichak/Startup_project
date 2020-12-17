<template>
  <div class="main_header">
    <b-navbar toggleable="md" type="info" variant="secondary">
      <b-navbar-brand class="logo" href="#">WebApp</b-navbar-brand>

      <b-navbar-toggle target="nav-collapse"></b-navbar-toggle>

      <b-collapse id="nav-collapse" is-nav>
        <b-navbar-nav>
          <b-nav-item href="#">Home</b-nav-item>
          <b-nav-item href="#" >Create</b-nav-item>
          <b-nav-item href="#">Load</b-nav-item>
        </b-navbar-nav>

        <!-- Right aligned nav items -->
        <b-navbar-nav class="ml-auto">
          <b-nav-form>
            <b-form-input size="sm" class="mr-sm-2" placeholder="Search"></b-form-input>
            <b-button size="sm" class="my-2 my-sm-0" type="submit">Search</b-button>
          </b-nav-form>
        </b-navbar-nav>
      </b-collapse>
    </b-navbar>
  </div>
</template>

<script>
export default {
  name: 'main_header',
  props: {

  }
}
</script>



<style scoped lang="scss">
a {
  color: #fff;
  }
.navbar :first-child :hover {
  color:#33D4FF;
}
.logo:hover {
  color:#33D4FF;
}
.nav-item :hover{
  color: #33D4FF;
}
.btn-secondary {
  color: #33D4FF;
  border: 1px solid #33d4ff;
  border-radius: 3px;
}
.main_header {
  margin-bottom: 20px;
}

</style>
