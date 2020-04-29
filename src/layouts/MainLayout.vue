<template>
  <q-layout view="lHh Lpr lFf">
    <q-header unelevated>
      <q-toolbar class="bg-grey">
        <q-btn
          flat
          dense
          round
          icon="menu"
          aria-label="menu"
          @click="leftDrawerOpen = !leftDrawerOpen"
        />

        <q-toolbar-title>
          Fiqyol Branded Clothes
        </q-toolbar-title>

        <div>Contact Person 082212345678</div>
      </q-toolbar>
    </q-header>

    <q-drawer
      v-model="leftDrawerOpen"
      show-if-above
      bordered
      content-class="bg-grey-1"
    >
      <q-list>
        <q-item-label
          header
          class="text-grey-8"
        >
          Ready From A To Z
        </q-item-label>
        <q-item clickable active-class="active" exact v-ripple :to="{ name: 'home'}">
          <q-item-section avatar>
            <q-icon name="home" />
          </q-item-section>

          <q-item-section>
            Menu
          </q-item-section>
        </q-item>
        <q-item clickable active-class="active" exact v-ripple :to="{ name: 'list'}">
          <q-item-section avatar>
            <q-icon name="list" />
          </q-item-section>

          <q-item-section>
            Shopping Lists
          </q-item-section>
        </q-item>
        <q-item clickable active-class="active" exact v-ripple :to="{ name: 'form'}">
          <q-item-section avatar>
            <q-icon name="input" />
          </q-item-section>

          <q-item-section>
            Input Form Shopping
          </q-item-section>
        </q-item>
        <q-item-label
          header
          class="text-grey-8"
        >
          About US
        </q-item-label>
        <EssentialLink
          v-for="link in essentialLinks"
          :key="link.title"
          v-bind="link"
        />
      </q-list>
    </q-drawer>

    <q-page-container class="bg-grey-3">
      <router-view />
    </q-page-container>
  </q-layout>
</template>

<script>
import EssentialLink from 'components/EssentialLink'

export default {
  name: 'MainLayout',

  components: {
    EssentialLink
  },

  data () {
    return {
      leftDrawerOpen: false,
      essentialLinks: [
        {
          title: 'Owner A',
          caption: 'IG Yollandha',
          icon: 'call',
          link: 'https://instagram.com/yollandhaaa'
        },
        {
          title: 'Owner B',
          caption: 'IG Fiqa',
          icon: 'call',
          link: 'https://instagram.com/strafiqa'
        }
      ]
    }
  }
}
</script>
