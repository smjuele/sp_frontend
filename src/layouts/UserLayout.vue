<template>
    <q-layout view="hHh Lpr lff">
      <q-header elevated class="bg-secondary">
        <q-toolbar>
          <q-btn flat @click="drawer = !drawer" icon="eva-menu-2-outline" />
          <q-toolbar-title class="q-pa-sm">JOPSIS
          </q-toolbar-title>
          <!-- <q-btn flat round dense icon="person" class="q-mr-xs" /> -->
        </q-toolbar>
      </q-header>

      <q-drawer
        v-model="drawer"
        show-if-above
        :mini="miniState"
        @mouseover="miniState = false"
        @mouseout="miniState = true"
        mini-to-overlay

        :width="300"
        :breakpoint="500"
        bordered
        content-class="bg-secondary"
      >
        <q-scroll-area class="fit q-pa-sm">
          <q-list padding class="q-mr-ma">
            <q-item clickable v-ripple @click="$router.push('/Homepage')">
              <q-item-section avatar>
                <q-icon name="home" color="white"/>
              </q-item-section>

              <q-item-section>
                Homepage
              </q-item-section>
            </q-item>

            <q-separator />

            <q-item clickable v-ripple @click="$router.push('/UserJobOrders')">
              <q-item-section avatar>
                <q-icon name="inbox" color="white"/>
              </q-item-section>

              <q-item-section>
                Job Order Requests
              </q-item-section>
            </q-item>

            <q-separator />

            <q-item clickable v-ripple @click="$router.push('/UserFileJobOrders')">
              <q-item-section avatar>
                <q-icon name="inbox" color="white"/>
              </q-item-section>

              <q-item-section>
                File Job Order Request
              </q-item-section>
            </q-item>

            <q-separator />

            <q-item clickable v-ripple @click="$router.push('/UserAccount')">
              <q-item-section avatar>
                <q-icon name="person" color="white" />
              </q-item-section>

              <q-item-section>
                Account Deatils
              </q-item-section>
            </q-item>

            <q-separator />

            <q-item clickable v-ripple>
              <q-item-section avatar>
                <q-icon name="eva-person-remove" color="white" />
              </q-item-section>

              <q-item-section @click="$router.push('/')">
                Log Out
              </q-item-section>
            </q-item>
          </q-list>
        </q-scroll-area>
      </q-drawer>

      <q-page-container class="page-container">
      <transition
              name="transitions"
              enter-active-class="animated fadeIn"
              leave-active-class="animated fadeOut"
              mode="out-in"
      >
        <router-view/>
      </transition>
      </q-page-container>
  </q-layout>
</template>

<script>
export default {
  data () {
    return {
      drawer: false,
      miniState: true
    }
  }
}
</script>

<style scoped>
.q-mr-ma {
  -webkit-text-fill-color: white;
}
</style>
