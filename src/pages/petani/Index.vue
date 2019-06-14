<template>
    <q-page padding>
        <q-table
        title="Petani"
        :data="data"
        :columns="columns"
        row-key="ktp"
        >
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
                @click="tambah()"
              />
        </template>
        </q-table>
    </q-page>
</template>
<script>
export default {
  data () {
    return {
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
          name: 'tempatlahir',
          field: 'tempatlahir',
          label: 'Tempat Lahir',
          align: 'center',
          sortable: true
        },
        {
          name: 'jeniskelamin',
          field: 'jeniskelamin',
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
          name: 'statuskeluarga',
          field: 'statuskeluarga',
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
          name: 'nohp',
          field: 'nohp',
          label: 'No Handphone',
          align: 'center',
          sortable: true
        },
        {
          name: 'namakelompoktani',
          field: 'namakelompoktani',
          label: 'Kelompok Tani',
          align: 'center',
          sortable: true
        }
      ],
      data: []
    }
  }
}
</script>
