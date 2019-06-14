<template>
    <q-page padding>
        <q-form
                @submit="onSubmit"
                @reset="onReset"
                class="q-gutter-md"
        >
            <q-input
                    filled
                    v-model="ktp"
                    label="Kartu Tanda Pengenal"
                    maxlength="15"
                    hint="KTP"
                    lazy-rules
                    :rules="[ val => val && val.length > 0 || 'Silahkan masukkan KTP']"
            />
            <q-input
                    filled
                    v-model="nama"
                    label="Nama Petani"
                    :rules="[ val => val && val.length > 0 || 'Silahkan masukkan Nama petani']"
                    maxlength="30"
                    hint="Nama Petani"
            />
            <q-input
                    filled
                    v-model="tempat_lahir"
                    label="Tempat Lahir"
                    hint="Tempat Lahir"
                    :rules="[ val => val && val.length > 0 || 'Silahkan masukkan Tempat Lahir']"
            />
            <q-input
                    filled
                    v-model="no_hp"
                    label="No Handphone"
                    maxlength="15"
                    :rules="[ val => val && val.length > 0 || 'Silahkan masukkan No Handphone']"
                    hint="No Handphone"
            />
            <q-input :rules="[ val => val && val.length > 0 || 'Silahkan masukkan Tanggal Lahyir', 'date']" filled v-model="tanggal_lahir" mask="date" label="Tanggal Lahir">
              <template v-slot:append>
                <q-icon name="event" class="cursor-pointer">
                  <q-popup-proxy ref="qDateProxy" transition-show="scale" transition-hide="scale">
                    <q-date v-model="tanggal_lahir" @input="() => $refs.qDateProxy.hide()" />
                  </q-popup-proxy>
                </q-icon>
              </template>
            </q-input>
            <div>
                <q-btn label="Submit" type="submit" color="primary"/>
                <q-btn label="Reset" type="reset" color="primary" flat class="q-ml-sm" />
            </div>
        </q-form>
    </q-page>
</template>
<script>
export default {
  data () {
    return {
      ktp: '',
      nama: '',
      no_hp: '',
      tanggal_lahir: '',
      tempat_lahir: ''
    }
  },
  methods: {
      onSubmit () {

      },
      onReset () {
      }
  }
}
</script>
