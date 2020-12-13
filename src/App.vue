<template>
    <div  id="app">
      <div class="container-fluid">
        <main_header />
        <div class="container">
          <doc_header/>
          <doc_group/>
          <doc_summary/>
          <page_footer/>
        </div>
      </div>
    </div>

</template>

<script>
import main_header from './components/main-header.vue'
import doc_header from './components/doc-header.vue'
import doc_group from './components/group/doc-group.vue'
import doc_summary from './components/doc-summary.vue'
import page_footer from "@/components/footer";

export default {
  name: 'App',
  components: {
    page_footer,
    main_header,
    doc_header,
    doc_group,
    doc_summary
  }
}
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  width: 960px;
  margin: 0 auto;
  height: 100vh;
}

</style>
