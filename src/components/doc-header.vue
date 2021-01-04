<template>
 <div class="container no-gutters">
   <div class="row  header_title">
     <div class="col offset-5 edit">
       <input
         placeholder="Document title"
         class="header_name"
         v-if="showEdit"
         type="text"
         v-model="title"
       />
       <div v-else class="title_name">
          <h4> {{title}} </h4>
       </div>
       <button class="btn_edit_doc_title" @click="edit" >
         <svg height="381pt" viewBox="0 -1 381.53417 381" width="381pt" xmlns="http://www.w3.org/2000/svg"><path d="m370.589844 230.964844c-5.523438 0-10 4.476562-10 10v88.792968c-.019532 16.558594-13.4375 29.980469-30 30h-280.589844c-16.5625-.019531-29.980469-13.441406-30-30v-260.589843c.019531-16.5625 13.4375-29.980469 30-30h88.789062c5.523438 0 10-4.476563 10-10 0-5.523438-4.476562-10-10-10h-88.789062c-27.601562.03125-49.96875 22.398437-50 50v260.589843c.03125 27.601563 22.398438 49.96875 50 50h280.589844c27.601562-.03125 49.96875-22.398437 50-50v-88.789062c0-5.523438-4.476563-10.003906-10-10.003906zm0 0"/><path d="m156.367188 178.34375 146.011718-146.015625 47.089844 47.089844-146.011719 146.015625zm0 0"/><path d="m132.542969 249.257812 52.039062-14.414062-37.625-37.625zm0 0"/><path d="m362.488281 7.578125c-9.769531-9.746094-25.585937-9.746094-35.355469 0l-10.605468 10.605469 47.089844 47.089844 10.605468-10.605469c9.75-9.769531 9.75-25.585938 0-35.355469zm0 0"/></svg>
       </button>
     </div>
     <div class="col-auto btn_save_container">
       <b-button variant="outline-warning" class="btn_save">Save</b-button>
     </div>
     <div class="col-auto add_group">
       <b-icon
           @click="addGroup"
           class="add_group_item"
           icon="plus-circle-fill"
           variant="success"
       />
     </div>
   </div>
   <div class="row align-items-center header_sub_title">
     <div class="col text-center">First Name</div>
     <div class="col text-center">Last Name</div>
     <div class="col text-center">Birthday</div>
     <div class="col text-center">Credit</div>
     <div class="col text-center">Spend</div>
   </div>
  <div class="groups">
    <div
        v-for="(item, index) in groups"
        :key="index"
        class="group"
    >
      <span>{{item.title}}</span>
      <span>{{item.subTitle}}</span>
    </div>
  </div>
 </div>

</template>

<script>
export default {
  name: "doc_header",
  props: {},
  data: () => ({
    title: '',
    showEdit: false,
    newGroup: {
      title: 'Group name',
      subTitle: 'Sub Title'
    },
    groups:[]
  }),
  methods: {
    edit() {
      this.showEdit = !this.showEdit
    },
    addGroup() {
      this.$emit('add-group')
    }

  }
}
</script>

<style scoped lang="scss">
.edit {
  display: flex;
  padding-left: 18px;
  margin-left: 41.666667%
}
.title_name h4 {
  padding-top: 1px;
  margin-top: 4px;
}
.header_name {
  border: 1px solid black;
  :focus {
    border:none;
  }
}
.header_title {
  display: flex;
  align-items: center;
  border: 1px solid black;
  border-bottom: none;
  border-top-right-radius: 5px;
  border-top-left-radius: 5px;
}
.btn_save_container {
  display: flex;
  justify-content: flex-end;
}
.btn_save {
  padding: 0 10px;
}
.header_sub_title {
  background-color: #B7BABB;
  height: 50px;
  border: 1px solid black;
  border-bottom-left-radius: 8px;
  border-bottom-right-radius: 8px;
  .col {
    border-right: 1px solid #fff;

  }
  .col {

    border-right: 1px solid #fff;
  }
  :last-child {
    border-right: none;
  }
}
.add_group {
  display: flex;
  justify-content: flex-end;
}
.add_group_item {

  width: 23px;
  height: 23px;
  margin-top: 2px;
  :hover {
    cursor: pointer;
  }
}
.btn_edit_doc_title {
  margin-left: 10px;
  border: 1px solid #fff;
  background: #ffffff;
  svg {
    display: inline-block;
    vertical-align: middle;
    width: 25px;
    height: 25px;

  }
}

</style>