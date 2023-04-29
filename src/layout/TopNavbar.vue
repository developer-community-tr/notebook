<template>
  <nav class="navbar navbar-expand-lg">
    <div class="container-fluid">
      <a class="navbar-brand" href="#">English Level is: B2, Upper Intermediate</a>
      <button type="button" class="navbar-toggler navbar-toggler-right" :class="{ toggled: $sidebar.showSidebar }"
        aria-controls="navigation-index" aria-expanded="false" aria-label="Toggle navigation" @click="toggleSidebar">
        <span class="navbar-toggler-bar burger-lines"></span>
        <span class="navbar-toggler-bar burger-lines"></span>
        <span class="navbar-toggler-bar burger-lines"></span>
      </button>
      <div class="collapse navbar-collapse justify-content-end">
        <ul class="nav navbar-nav mr-auto">
          <li class="nav-item">
            <a class="nav-link" href="#" data-toggle="dropdown">
              <i class="nc-icon nc-chart-bar-32"></i>
            </a>
          </li>

          <li class="nav-item">
            <form @submit="searchSubmit">
              <div class="form-group">
                <input type="text" class="form-control" id="searchInput" aria-describedby="searchHelp"
                  v-model="searchInput" placeholder="Search a word">
                <button type="submit" class="btn btn-primary" id="searchButton">Search</button>
              </div>
            </form>
          </li>
        </ul>
        <ul class="navbar-nav ml-auto">
          <li class="nav-item">
            <a class="nav-link" href="#/who-am-i">
              Who are we?
            </a>
          </li>

        </ul>
      </div>
    </div>
  </nav>
</template>
<script>
import StaticData from 'src/components/Data/StaticData.vue';

export default {
  components: {
    StaticData,
  },
  computed: {
    routeName() {
      const { name } = this.$route
      return this.capitalizeFirstLetter(name)
    }
  },
  data() {
    return {
      activeNotifications: false
    }
  },
  methods: {
    searchSubmit() {
      this.$router.push({ name: 'SearchResult', params: { content: this.searchInput } })
    },
    capitalizeFirstLetter(string) {
      return string.charAt(0).toUpperCase() + string.slice(1)
    },
    toggleNotificationDropDown() {
      this.activeNotifications = !this.activeNotifications
    },
    closeDropDown() {
      this.activeNotifications = false
    },
    toggleSidebar() {
      this.$sidebar.displaySidebar(!this.$sidebar.showSidebar)
    },
    hideSidebar() {
      this.$sidebar.displaySidebar(false)
    }
  }
}

</script>
<style>
#searchInput {
  width: 175px;
  float: left;
  margin: -10px 4px 0px 12px;
}

#searchButton {
  float: left;
  margin: -10px 0px 0px 0px;
  padding: 7px;
}
</style>
