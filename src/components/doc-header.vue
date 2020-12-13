<template>
 <div class="container no-gutters">
   <div class="row header_title">
     <div class="col col-10 edit">
       <input
         v-if="showEdit"
         type="text"
         v-model="title"
       />
       <div v-else>{{title}}</div>

       <button @click="edit" >edit</button>
     </div>
     <div class="col">
       <b-button variant="outline-warning" class="btn_save">Save</b-button>
     </div>
     <div class="col add_group">
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
      this.groups.push(this.newGroup)
    }
  }
}
</script>



<style scoped lang="scss">
.edit {
  display: flex;
}
.header_title {
  display: flex;
  align-items: center;
  border: 1px solid black;
  border-bottom: none;
  border-top-right-radius: 5px;
  border-top-left-radius: 5px;
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
.add_group_item {
  width: 23px;
  height: 23px;
  margin-top: 2px;
  :hover {
    cursor: pointer;
  }
}



</style>