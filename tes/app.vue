<template>
  <div>
    <SiswaForm @siswa-added="addSiswa" />
    <DaftarSiswa :siswaList="siswaList" />
  </div>
</template>

<script>
import 'bootstrap/dist/css/bootstrap.css'
import SiswaForm from '@/components/SiswaForm.vue';
import DaftarSiswa from '@/components/DaftarSiswa.vue';

export default {
  components: {
    SiswaForm,
    DaftarSiswa
  },
  data() {
    return {
      siswaList: []
    };
  },
  methods: {
    addSiswa(siswa) {
      this.siswaList.push(siswa);
    }
  }
};
</script>
