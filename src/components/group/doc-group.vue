<template>
  <div class="container group_header_container">
    <div class="row group_header">
      <div class="col">
        <button class="btn_collapse">
          <svg id="Layer" enable-background="new 0 0 64 64" height="512" viewBox="0 0 64 64" width="512" xmlns="http://www.w3.org/2000/svg"><path d="m26.586 34.586-14.586 14.586v-5.172c0-1.104-.896-2-2-2s-2 .896-2 2v10c0 1.104.896 2 2 2h10c1.104 0 2-.896 2-2s-.896-2-2-2h-5.172l14.586-14.586c.781-.781.781-2.047 0-2.828-.78-.781-2.048-.781-2.828 0z"/><path d="m54 8h-10c-1.104 0-2 .896-2 2s.896 2 2 2h5.172l-14.586 14.586c-.781.781-.781 2.047 0 2.828.391.391.902.586 1.414.586s1.023-.195 1.414-.586l14.586-14.586v5.172c0 1.104.896 2 2 2s2-.896 2-2v-10c0-1.104-.896-2-2-2z"/></svg>
        </button>
      </div>
      <div class="col edit">
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
        <b-modal v-b-modal="modalShow">would you like to delete</b-modal>
      </div>
      <div class="col">
        <b-button class="btn_delete_class" @click="deleteGroup">
          <svg height="512pt" viewBox="-57 0 512 512" width="512pt" xmlns="http://www.w3.org/2000/svg"><path d="m156.371094 30.90625h85.570312v14.398438h30.902344v-16.414063c.003906-15.929687-12.949219-28.890625-28.871094-28.890625h-89.632812c-15.921875 0-28.875 12.960938-28.875 28.890625v16.414063h30.90625zm0 0"/><path d="m344.210938 167.75h-290.109376c-7.949218 0-14.207031 6.78125-13.566406 14.707031l24.253906 299.90625c1.351563 16.742188 15.316407 29.636719 32.09375 29.636719h204.542969c16.777344 0 30.742188-12.894531 32.09375-29.640625l24.253907-299.902344c.644531-7.925781-5.613282-14.707031-13.5625-14.707031zm-219.863282 312.261719c-.324218.019531-.648437.03125-.96875.03125-8.101562 0-14.902344-6.308594-15.40625-14.503907l-15.199218-246.207031c-.523438-8.519531 5.957031-15.851562 14.472656-16.375 8.488281-.515625 15.851562 5.949219 16.375 14.472657l15.195312 246.207031c.527344 8.519531-5.953125 15.847656-14.46875 16.375zm90.433594-15.421875c0 8.53125-6.917969 15.449218-15.453125 15.449218s-15.453125-6.917968-15.453125-15.449218v-246.210938c0-8.535156 6.917969-15.453125 15.453125-15.453125 8.53125 0 15.453125 6.917969 15.453125 15.453125zm90.757812-245.300782-14.511718 246.207032c-.480469 8.210937-7.292969 14.542968-15.410156 14.542968-.304688 0-.613282-.007812-.921876-.023437-8.519531-.503906-15.019531-7.816406-14.515624-16.335937l14.507812-246.210938c.5-8.519531 7.789062-15.019531 16.332031-14.515625 8.519531.5 15.019531 7.816406 14.519531 16.335937zm0 0"/><path d="m397.648438 120.0625-10.148438-30.421875c-2.675781-8.019531-10.183594-13.429687-18.640625-13.429687h-339.410156c-8.453125 0-15.964844 5.410156-18.636719 13.429687l-10.148438 30.421875c-1.957031 5.867188.589844 11.851562 5.34375 14.835938 1.9375 1.214843 4.230469 1.945312 6.75 1.945312h372.796876c2.519531 0 4.816406-.730469 6.75-1.949219 4.753906-2.984375 7.300781-8.96875 5.34375-14.832031zm0 0"/></svg>
        </b-button>
      </div>
      <div class="col-auto justify-content-center">
        <b-icon
          @click="addRow"
          class="add_group_row"
          icon="plus-circle-fill"
          variant="success"
        />
      </div>
    </div>

    <doc_row
      v-for="(row, index) in group.rows"
      :row="row"
      :id="group.id"
      :key="index"
      @delete-row ="deleteRow($event)"
      @duplicate-row ="duplicateRow($event)"
    />

    <doc-row-2/>
  </div>
</template>

<script>
import doc_row from '@/components/doc-row.vue'
import DocRow2 from "@/components/doc-row-2";

export default {
  name: "doc_group",
  components: {
    DocRow2,
    doc_row
  },
  props: ['group'],
  data: () => ({
    title: '',
    showEdit:false,
    modalShow: false,
    newRow: {
      id: 1,
      name: 'newRowName',
      lastName: 'newRowLastName',
      bd: 'newRowBD',
      spend: 'newRowSpend',
      credit: 'newRowCredit'
    }
  }),
  methods: {
    edit() { this.showEdit = !this.showEdit },
    addRow() {
      this.group.rows.push(this.newRow)
    },
    deleteGroup() {
      this.$emit('delete-group', this.group.id)
    },
    deleteRow (rowId) {
     this.group.rows = this.group.rows.filter( item => item.id !== rowId )
    },
    duplicateRow (duplicatedRow) {
      this.group.rows.push(duplicatedRow)
    }
  }
}
</script>

<style scoped lang="scss">
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
.edit {
  display: flex;
  padding-left: 10rem;
}
.btn_delete_class {
  border: 1px solid #fff;
  background: #ffffff;
  svg {
    display: inline-block;
    vertical-align: middle;
    width: 25px;
    height: 25px;
  }
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
.group_header_container {
  margin-top: 30px;
  .group_header {
    border: 1px solid #000;
    border-top-right-radius: 5px;
    border-top-left-radius: 5px;
  }
}
.add_group_row {
  width: 23px;
  height: 23px;
  margin-top: 8px;
  :hover {
    cursor: pointer;
  }
}
.title_name h4 {
  margin-bottom: 0;
  padding-top: 2px;
  margin-top: 4px;
}
</style>