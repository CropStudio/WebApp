<template>
  <q-page padding>
    <q-table title="Petani" :data="data" :columns="columns" row-key="ktp" :loading="loading">
      <template v-slot:top>
        <q-space/>
        <q-input outlined dense debounce="300" color="primary" v-model.trim="filter">
          <template v-slot:append>
            <q-icon name="search"/>
          </template>
        </q-input>
        <q-btn
          icon="add"
          unelevated
          label="Tambah"
          size="sm"
          class="q-ml-xs q-mr-xs q-pa-sm bg-green-5 text-white"
          dense
          to="/petani/add"
        />
      </template>
    </q-table>
  </q-page>
</template>
<script>
export default {
  data () {
    return {
      filter: '',
      columns: [
        {
          name: 'ktp',
          field: 'ktp',
          label: 'Kartu Tanda Pengenal',
          align: 'left',
          sortable: true
        },
        {
          name: 'nama',
          field: 'nama',
          label: 'Nama Petani',
          align: 'center',
          sortable: true
        },
        {
          name: 'tempat_lahir',
          field: 'tempat_lahir',
          label: 'Tempat Lahir',
          align: 'center',
          sortable: true
        },
        {
          name: 'tanggal_lahir',
          field: 'tanggal_lahir',
          label: 'Tanggal Lahir',
          align: 'center',
          sortable: true
        },
        {
          name: 'jenis_kelamin',
          field: 'jenis_kelamin',
          label: 'Jenis Kelamin',
          align: 'center',
          sortable: true
        },
        {
          name: 'pendidikan',
          field: 'pendidikan',
          label: 'Pendidikan Terakhir',
          align: 'center',
          sortable: true
        },
        {
          name: 'status_keluarga',
          field: 'status_keluarga',
          label: 'Status Keluarga',
          align: 'center',
          sortable: true
        },
        {
          name: 'alamat',
          field: 'alamat',
          label: 'Alamat',
          align: 'center',
          sortable: true
        },
        {
          name: 'no_hp',
          field: 'no_hp',
          label: 'No Handphone',
          align: 'center',
          sortable: true
        },
        {
          name: 'nama_kelompok_petani',
          field: 'nama_kelompok_petani',
          label: 'Kelompok Tani',
          align: 'center',
          sortable: true
        }
      ],
      data: [],
      loading: false
    }
  },
  methods: {
    loadData () {
      this.loading = true
      this.$axios.get('datapetani').then(({ data }) => {
        this.loading = false
        if (data.status) {
          this.data = data.message
        } else {
          this.$q.notify({
            message: 'Gagal load data/tidak ada data!',
            color: 'negative',
            icon: 'close'
          })
        }
      })
    }
  },
  mounted () {
    this.loadData()
  }
}
</script>
