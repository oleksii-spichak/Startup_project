<template>
    <b-row class="row_1" align-v="center">
      <div class="col-1 btn_container_drag_drop ">
        <button>
          <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" fill="currentColor" class="bi bi-three-dots-vertical" viewBox="0 0 16 16">
            <path fill-rule="evenodd" d="M9.5 13a1.5 1.5 0 1 1-3 0 1.5 1.5 0 0 1 3 0zm0-5a1.5 1.5 0 1 1-3 0 1.5 1.5 0 0 1 3 0zm0-5a1.5 1.5 0 1 1-3 0 1.5 1.5 0 0 1 3 0z"/>
          </svg>
        </button>
      </div>
      <div class="col-2 first_name">
        <input
            placeholder="First Name"
            class="row_first_name"
            type="text"
        />
      </div>
      <div class="col-2 last_name">
        <input
            placeholder="Last Name"
            class="row_last_name"
            type="text"
        />
      </div>
      <div class="col-2 birthday">
        <input
            placeholder="Birthday"
            class="row_date_birthday"
            type="text"
        />
      </div>
      <div class="col-2 credit">
        <input
            placeholder="Credit"
            class="row_user_credit"
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
name: "doc_row",
  props:{},
}
</script>

<style scoped lang="scss">

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
.dropright_item {
  background-color: #becbbe;
}
.row_1 {
  height: 50px;
  width: 900px;
  border: 1px solid #000000;
  margin-right: 15px;
  margin-bottom: 2px;
  input {
    width: 140px;
    height: 50px;
  }
}
.col-2 {
  height: 50px;
  margin-left: -3px;
}
.dropright {
  top: 0;
  right: -49px;
  padding-right: 0;
  height: 47px;
  padding-left: 0;
}
.first_name {
  right: 20px;
}
.last_name {
  right: -8px;
}
.birthday {
  right: -42px;
}
.credit {
  right: -70px;
}
.spend {
  right: -90px;
}
</style>