<template>
  <div class="home">
    
    <SearchPanel />
  </div>
</template>

<script>
// @ is an alias to /src
import SearchPanel from '@/components/SearchPanel.vue'

export default {
  name: 'Home',
  components: {
    SearchPanel
  }
}
</script>
