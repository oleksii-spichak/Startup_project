<template>
    <div  id="app">
      <b-modal id="modal-test" @ok="deleteGroup($event)">
        <template #modal-title>
          <p>Hello User</p>
        </template>
        <div class="d-block text-center">
          <h3>Would you like to delete row?</h3>
        </div>
      </b-modal>

      <div class="container-fluid">
        <main_header />
        <div class="container">
          <doc_header @add-group="addGroup"/>

          <div>
            <doc_group
                v-for="(group, index) in groups"
                :key="index"
                :group="group"
                @delete-group="showModal($event)"
            />
          </div>

<!--          <doc_summary/>-->
<!--          <page_footer/>-->
        </div>
      </div>
    </div>

</template>

<script>
import main_header from './components/main-header.vue'
import doc_header from './components/doc-header.vue'
import doc_group from './components/group/doc-group.vue'
import doc_summary from './components/summary/doc-summary.vue'
import page_footer from "@/components/footer";

export default {
  name: 'App',
  components: {
    page_footer,
    main_header,
    doc_header,
    doc_group,
    doc_summary
  },
  data: () => ({
    groupToDeleteId: null,
    newGroup: {
      id: 33,
      rows: []
    },
    groups: [
      {
        id: 1,
        rows: [
          {
            id: 11,
            name: 'name 11',
            lastName: 'lastName 11',
            bd: 'bd 11',
            credit: 'credit 11',
            spend: 'spend11',
          },
          {
            id: 12,
            name: 'name 12',
            lastName: 'lastName 12 ',
            bd: 'bd12',
            credit: 'credit12',
            spend: 'spend12',
          }
        ]
      },
      {
        id: 2,
        rows: [
          {
            id: 21,
            name: 'name 21',
            lastName: 'lastName 21',
            bd: 'bd 21',
            credit: 'credit 21',
            spend: 'spend 21',
          },
          {
            id: 22,
            name: 'name 22',
            lastName: 'lastName 22',
            bd: 'bd 22',
            credit: 'credit 22',
            spend: 'spend 22',
          }
        ]
      },
      {
        id: 3,
        rows: [
          {
            id: 21,
            name: 'name 21',
            lastName: 'lastName 21',
            bd: 'bd 21',
            credit: 'credit 21',
            spend: 'spend 21',
          },
          {
            id: 22,
            name: 'name 22',
            lastName: 'lastName 22',
            bd: 'bd 22',
            credit: 'credit 22',
            spend: 'spend 22',
          }
        ]
      },
      {
        id: 4,
        rows: [
          {
            id: 21,
            name: 'name 21',
            lastName: 'lastName 21',
            bd: 'bd 21',
            credit: 'credit 21',
            spend: 'spend 21',
          },
          {
            id: 22,
            name: 'name 22',
            lastName: 'lastName 22',
            bd: 'bd 22',
            credit: 'credit 22',
            spend: 'spend 22',
          }
        ]
      }
    ]
  }),
  methods: {
    addGroup() {
      this.groups.push(this.newGroup)
    },
    deleteGroup(event) {
      if(event.trigger === 'ok') {
        this.groups = this.groups.filter(item => item.id !== this.groupToDeleteId)
        this.$bvModal.hide('modal-test')
      }
    },
    showModal(deleteGroupId) {
      this.groupToDeleteId = deleteGroupId
      this.$bvModal.show('modal-test')
    },
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
