<template>
  <div>
    <v-card color="#4281a4">
      <v-card-title>
        <v-spacer />
        <v-text-field
          v-model="search"
          append-icon="mdi-magnify"
          label="Search"
          single-line
          hide-details
        />
      </v-card-title>
      <v-data-table
        :headers="headers"
        :items="desserts"
        :items-per-page="5"
        :search="search"
        class="elevation-3"
      />
    </v-card>
  </div>
</template>

<script>
export default {
  data () {
    return {
      search: '',
      headers: [
        {
          text: 'ชื่อผู้จอง',
          align: 'start',
          sortable: false,
          value: 'name'
        },
        {
          text: 'E-mail',
          value: 'email'
        },
        {
          text: 'เบอร์โทร',
          value: 'phone'
        },
        {
          text: 'ที่อยู่',
          value: 'address.add'
        },
        {
          text: 'ตำบล/แขวง',
          value: 'address.sub_district'
        },
        {
          text: 'อำเภอ/เขต',
          value: 'address.district'
        },
        {
          text: 'จังหวัด',
          value: 'address.province'
        },
        {
          text: 'จำนวนห้อง',
          value: 'room'
        },
        {
          text: 'จำนวนคน',
          value: 'costumers'
        },
        {
          text: 'จองวันที่',
          value: 'date_in'
        },
        {
          text: 'ถึงวันที่',
          value: 'date_out'
        }
      ]
    }
  },
  computed: {
    desserts: {
      get () {
        return this.$nuxt.$store.state.list
      }
    }
    // listdata: {},
  }
}
</script>
