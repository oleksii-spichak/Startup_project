<template>
<div class="row">
  <div class="col-1 ">
    <button>
      <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" fill="currentColor" class="bi bi-three-dots-vertical" viewBox="0 0 16 16">
        <path fill-rule="evenodd" d="M9.5 13a1.5 1.5 0 1 1-3 0 1.5 1.5 0 0 1 3 0zm0-5a1.5 1.5 0 1 1-3 0 1.5 1.5 0 0 1 3 0zm0-5a1.5 1.5 0 1 1-3 0 1.5 1.5 0 0 1 3 0z"/>
      </svg>
    </button>
  </div>
  <div class="col-2">
    <input
        placeholder="First Name"
        class="row_first_name"
        type="text"
    />
  </div>
  <div class="col-2">
    <input
        placeholder="Last Name"
        class="row_last_name"
        type="text"
    />
  </div>
  <div class="col-2">
    <input
        placeholder="Birthday"
        class="row_date_birthday"
        type="text"
    />
  </div>
  <div class="col-2">
    <input
        placeholder="Credit"
        class="row_user_credit"
        type="text"
    />
  </div>
  <div class="col-2">
    <input
        placeholder="Spend"
        class="row_user_spend"
        type="text"
    />
  </div>
  <div class="col-1">
    <b-dropdown id="dropdown-dropright" dropright text="" variant="Secondary" class="dropright_item">
      <b-dropdown-item href="#">Duplicate</b-dropdown-item>
      <b-dropdown-item href="#">Remove</b-dropdown-item>
      <b-dropdown-item href="#">Move to...</b-dropdown-item>
    </b-dropdown>
  </div>
  <div class="row ">
    <div class="col-1 ">
      <button>
        <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" fill="currentColor" class="bi bi-three-dots-vertical" viewBox="0 0 16 16">
          <path fill-rule="evenodd" d="M9.5 13a1.5 1.5 0 1 1-3 0 1.5 1.5 0 0 1 3 0zm0-5a1.5 1.5 0 1 1-3 0 1.5 1.5 0 0 1 3 0zm0-5a1.5 1.5 0 1 1-3 0 1.5 1.5 0 0 1 3 0z"/>
        </svg>
      </button>
    </div>
    <div class="col">
      <b-form-select v-model="selected" :options="options"></b-form-select>
    </div>
    <div class="col">Input Last Name</div>
    <div class="col">Data picker</div>
    <div class="col">
      <input
          placeholder="Spend"
          class="row_user_spend"
          type="text"
      />
    </div>
    <div class="col">
      <input
        placeholder="Spend"
        class="row_user_spend"
        type="text"
    />
    </div>
    <div class="col-1">
      <b-dropdown id="dropdown-dropright" dropright text="" variant="Secondary" class="dropright_item">
        <b-dropdown-item href="#">Duplicate</b-dropdown-item>
        <b-dropdown-item href="#">Remove</b-dropdown-item>
        <b-dropdown-item href="#">Move to...</b-dropdown-item>
      </b-dropdown>
    </div>
  </div>

</div>

</template>

<script>
export default {
name: "doc_row",
  props:{},
  data () {
   return {
     selected: null,
     options: [
       {value: null, text: 'Select'},
       {text: 'Name 1'},
       {text: 'Name 2'},
       {text: 'Name 3'},

     ]
   }
  }
}
</script>

<style scoped lang="scss">


.dropright_item {
  background-color: #becbbe;
}
</style>