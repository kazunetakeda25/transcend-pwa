<template>
  <v-bottom-navigation
    v-model="bottomNav"
    shift
    class="primary"
    grow
    style="border-top-left-radius: 4px;border-top-right-radius: 4px;"
  >
    <v-btn min-width="60">
      <span style="color: white;">Schedule</span>
      <v-icon color="white">
        mdi-calendar-text
      </v-icon>
    </v-btn>

    <v-btn min-width="60">
      <span style="color: white;">Jobs for Bid</span>
      <v-icon color="white" style="font-size: 26px">
        mdi-layers
      </v-icon>
    </v-btn>

    <v-btn min-width="60">
      <span style="color: white;">Completed</span>
      <v-icon color="white">
        mdi-checkbox-multiple-marked
      </v-icon>
    </v-btn>

    <v-btn min-width="60">
      <span style="color: white;">Message</span>
      <v-icon color="white">
        mdi-message-text
      </v-icon>
    </v-btn>

    <v-btn min-width="60">
      <span style="color: white;">Profile</span>
      <v-icon color="white" style="font-size: 28px">
        mdi-account
      </v-icon>
    </v-btn>
  </v-bottom-navigation>
</template>

<style scoped>

</style>

<script>
export default {
  data () {
    return {
      bottomNav: 1
    }
  },

  computed: {
    color () {
      switch (this.bottomNav) {
        case 0: return 'schedule'
        case 1: return 'jobs-for-bid'
        case 2: return 'completed'
        case 3: return 'message'
        case 4: return 'profile'
      }

      return 'jobs-for-bid'
    }
  }
}
</script>
