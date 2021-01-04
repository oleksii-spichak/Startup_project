<template>
  <b-row class="summary_data">
    <b-col>
      <div>
        <b-form-input placeholder="First Name"></b-form-input>
      </div>
    </b-col>
    <b-col>
      <div>
        <b-form-input placeholder="Last Name"></b-form-input>
      </div>
    </b-col>
    <b-col>
      <div>
        <b-form-input placeholder="Birthday"></b-form-input>
      </div>
    </b-col>
    <b-col>
      <div>
        <b-form-input placeholder="Credit" readonly></b-form-input>
      </div>
    </b-col>
    <b-col class="summary_spend">
      <div>
        <b-form-input placeholder="Spend" readonly></b-form-input>
      </div>
    </b-col>
  </b-row>
</template>

<script>
export default {
  name: "doc_summary_row"
}
</script>

<style scoped lang="scss">
.summary_data .col {
  border: 1px solid #000;
  border-right: none ;
  input {
    width: 145px;
  }
}
.summary_spend {
  border-right: 1px solid #000 !important;
}

</style>