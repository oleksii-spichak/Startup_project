<template>
<b-container class="summary_container">
  <b-row class="summary_row">
    <b-col cols="1">
      <button class="btn_collapse">
        <svg id="Layer" enable-background="new 0 0 64 64" height="512" viewBox="0 0 64 64" width="512" xmlns="http://www.w3.org/2000/svg"><path d="m26.586 34.586-14.586 14.586v-5.172c0-1.104-.896-2-2-2s-2 .896-2 2v10c0 1.104.896 2 2 2h10c1.104 0 2-.896 2-2s-.896-2-2-2h-5.172l14.586-14.586c.781-.781.781-2.047 0-2.828-.78-.781-2.048-.781-2.828 0z"/><path d="m54 8h-10c-1.104 0-2 .896-2 2s.896 2 2 2h5.172l-14.586 14.586c-.781.781-.781 2.047 0 2.828.391.391.902.586 1.414.586s1.023-.195 1.414-.586l14.586-14.586v5.172c0 1.104.896 2 2 2s2-.896 2-2v-10c0-1.104-.896-2-2-2z"/></svg>
      </button>
    </b-col>
    <b-col class="text-center">
      <h5 class="summary_title">
        <span>Summary</span>
      </h5>
    </b-col>
  </b-row>
  <doc_summary_row/>
</b-container>
</template>

<script>
import doc_summary_row from '@/components/summary/doc-summary-row'



export default {
  name: "doc_summary",
  components: {
    doc_summary_row
  }
}
</script>

<style scoped lang="scss">
.summary_row {
  border: 1px solid #000;
  border-top-left-radius: 10px;
  border-top-right-radius: 10px;
}
.btn_collapse {
  border: 1px solid #fff;
  background: #ffffff;
  margin-top: 3px;
  svg {
    display: inline-block;
    vertical-align: middle;
    width: 25px;
    height: 25px;
  }
}
.summary_container {
  position: absolute;
  top:475px;
  max-width: 900px;
}
</style>