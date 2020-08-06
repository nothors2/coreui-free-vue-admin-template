<template>
  <div>
    <CRow>
      <CCol lg="6">
        <CTableWrap :items="getShuffledUsersData()">
          <template #header>
            <CIcon name="cil-grid"/> Simple Table
            <div class="card-header-actions">
              <a 
                href="https://coreui.io/vue/docs/components/nav" 
                class="card-header-action" 
                rel="noreferrer noopener" 
                target="_blank"
              >
                <small class="text-muted">docs</small>
              </a>
            </div>
          </template>
        </CTableWrap>
      </CCol>

      <CCol lg="6">
        <CTableWrap
          :items="getShuffledUsersData()"
          striped
          caption="Striped Table"
        />
      </CCol>
    </CRow>

    <CRow>
      <CCol lg="6">
        <CTableWrap
          :items="getShuffledUsersData()"
          small
          caption="Condensed Table"
        />
      </CCol>

      <CCol lg="6">
        <CTableWrap
          :items="getShuffledUsersData()"
          fixed
          border
          caption="Bordered Table"
        />
      </CCol>
    </CRow>

    <CRow>
      <CCol sm="12">
        <CTableWrap
          :items="getShuffledUsersData()"
          hover
          striped
          border
          small
          fixed
          sorter
          caption="Combined All Table"
        />
      </CCol>
    </CRow>

    <CRow>
      <CCol sm="12">
        <CTableWrap
          :items="getShuffledUsersData()"
          hover
          striped
          border
          small
          fixed
          sorter
          dark
          caption="Combined All dark Table"
        />
      </CCol>
    </CRow>
  </div>
</template>

<script>
import CTableWrap from './Table.vue'
import usersData from '../users/UsersData2'

export default {
  name: 'Tables',
  components: { CTableWrap },
  methods: {
    shuffleArray (array) {
      for (let i = array.length - 1; i > 0; i--) {
        let j = Math.floor(Math.random() * (i + 1))
        let temp = array[i]
        array[i] = array[j]
        array[j] = temp
      }
      return array
    },

    getShuffledUsersData () {
      return this.shuffleArray(usersData.slice(0))
    }
  }
}
</script>
