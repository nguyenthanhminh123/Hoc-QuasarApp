<template>
  <q-layout view="lHh Lpr lFf">
    <q-header elevated>
      <q-toolbar>
        <q-btn
          flat
          dense
          round
          icon="menu"
          @click="toggleLeftDrawer"
          aria-label="Menu"
        /> 

        <q-toolbar-title> 
          Quasar App 
        </q-toolbar-title>

        <div>Quasar v{{ $q.version }}</div>
      </q-toolbar>
    </q-header>

    <q-footer>
      <q-tabs>
        <q-route-tab 
        to="/"
          icon="list" 
          label="Todo" />
        <q-route-tab
          to="/settings" 
          icon="settings" 
          label="Settings" />
      </q-tabs>
    </q-footer>

    <q-drawer 
    v-model="leftDrawerOpen" 
    bordered
    content-class="bg-grey-2"
    >
      <q-list>
        <q-item-label header> Navigation </q-item-label>

          <q-item 
            v-for="nav in navs"
            to="/"
            exact
            clickable> 
            <q-item-section avatar>
              <q-icon name="list"/>
            </q-item-section>
            <q-item-section>
              <q-item-label>Todo</q-item-label>
            </q-item-section>
          </q-item>

      </q-list>
    </q-drawer>

    <q-page-container>
      <router-view />
    </q-page-container>
  </q-layout>
</template>

<script>
  import { openURL } from 'quasar'

  export default {
    name: 'Mylayout',
    data() {
      return {
        leftDrawerOpen: this.$q.platform.is.desktop,
        navs: [
          {
            label: 'Todo',
            icon: 'list',
            to: '/'
          },
          {
            label: 'Settings',
            icon: 'setting',
            to: '/'
          }
        ]
      }
    },
    methods: {
      openURL
    }
  }
</script>
