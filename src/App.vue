<template>
  <div id="app">
    <Tab/>
    <div class="body">
      <router-view/>
    </div>
  </div>
</template>

<script>
import Tab from '@/components/Tab'
import '@/assets/style.scss'

export default {
  name: 'App',
  components: { Tab }
}
</script>
