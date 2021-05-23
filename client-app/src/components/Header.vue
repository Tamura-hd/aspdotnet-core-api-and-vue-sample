<template>
  <q-header elevated class="glossy">
    <q-toolbar>
      <q-btn
        flat
        dense
        round
        @click="$emit('update:leftDrawerOpen', !leftDrawerOpen)"
        aria-label="Menu"
        icon="menu"
      />

      <q-toolbar-title>
        Quasar App
      </q-toolbar-title>

      <div>Quasar v{{ $q.version }}</div>
    </q-toolbar>
  </q-header>
</template>

<script>
export default {
  name: 'Header',
  props: {
    leftDrawerOpen: Boolean,
  },

  data () {
    return {
    }
  }
}
</script>