<template>
  <b-row class="row row_2" align-v="">
    <div class="col-1 btn_container_drag_drop">
      <button>
        <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" fill="currentColor" class="bi bi-three-dots-vertical" viewBox="0 0 16 16">
          <path fill-rule="evenodd" d="M9.5 13a1.5 1.5 0 1 1-3 0 1.5 1.5 0 0 1 3 0zm0-5a1.5 1.5 0 1 1-3 0 1.5 1.5 0 0 1 3 0zm0-5a1.5 1.5 0 1 1-3 0 1.5 1.5 0 0 1 3 0z"/>
        </svg>
      </button>
    </div>
    <div class="col-2 selected_name_wrapper">
      <b-form-select v-model="selected1" :options="options" class="selected_name"></b-form-select>
    </div>
    <div class="col-2 user_input_lastname">
      <input
          placeholder="Input Last Name"
          class="row_user_input_lastname"
          type="text"
      />
    </div>
    <div class="col-3 date_picker_inner">
      <b-input-group class="date_picker_wrapper">
        <b-form-input
            class="date_input"
            id="example-input"
            v-model="value"
            type="text"
            placeholder="Choose Date"
            autocomplete="off"
        ></b-form-input>
        <b-input-group-append>
          <b-form-datepicker
              class="date_picker_button"
              v-model="value"
              button-only
              right
              locale="en-US"
              aria-controls="example-input"
              @context="onContext"
          ></b-form-datepicker>
        </b-input-group-append>
      </b-input-group>


    </div>
    <div class="col-2 credit">
      <input
          placeholder="Credit"
          class="row_user_spend"
          type="text"
      />
    </div>
    <div class="col-2 spend">
      <input
          placeholder="Spend"
          class="row_user_spend"
          type="text"
      />
    </div>
    <div class="col-1 dropright">
      <b-dropdown id="dropdown-dropright" dropright text="" variant="Secondary" class="dropright_item">
        <b-dropdown-item href="#">Duplicate</b-dropdown-item>
        <b-dropdown-item href="#">Remove</b-dropdown-item>
        <b-dropdown-item href="#">Move to...</b-dropdown-item>
      </b-dropdown>
    </div>
  </b-row>
</template>

<script>
export default {
name: "doc-row-2",
  props: {},
  data () {
  return {
    selected1: null,
    options: [
      {value: null, text: 'Select'},
      {text: 'Name 1'},
      {text: 'Name 2'},
      {text: 'Name 3'},

    ],
    value: '',
    formatted: '',
    selected: ''
  }
  },
  methods: {
  onContext (ctx) {
    this.formatted = ctx.selectedFormatted
    this.selected = ctx.selectedYMD
  }
  }
}
</script>

<style lang="scss" scoped>
.row_2 {
  height: 50px;
  border: 1px solid #000000;
}
.col-2 {
  height: 50px;
  margin-left: -3px;
  input {
    width: 140px;
    height: 47px;
  }
}
.btn_container_drag_drop {
  padding: 0;
  max-width: 4%;
  button {
    height: 50px;
    width: 20px;
  }
  svg {
    display: inline-block;
    vertical-align: middle;
    width: 34px;
    height: 34px;
    position: absolute;
    top: 8px;
    right: 8px;
  }
}
.selected_name {
  height: 45px;
  width: 140px;

}
.date_picker_wrapper {
  height: 47px;
  .date_input {
    height: 47px;
  }
}
.user_input_lastname {
 left: 7px;
}
.selected_name_wrapper {
  left: -20px
}
.date_picker_inner {
  left: 20px;
}
.credit {
  left: -7px;
}
.spend {
  left: 13px;
}
.dropright_item {
  background-color: #becbbe;
}
.dropright {
  top: -25px;
  right: -433px;
  padding-right: 0;
  height: 47px;
  padding-left: 0;
}
</style>