<template>
    <div>
      <h2>Daftar Siswa</h2>
      <ul>
        <li v-for="(siswa, index) in siswaList" :key="index">
          {{ siswa.induk }} - {{ siswa.nama }} - {{ siswa.nilai }}
        </li>
      </ul>
      <h3>Rata-rata Nilai Tugas: {{ rataRataNilai }}</h3>
    </div>
  </template>
  
  <script>
  export default {
    props: {
      siswaList: {
        type: Array,
        default: () => []
      }
    },
    computed: {
      rataRataNilai() {
        if (this.siswaList.length === 0) {
          return 0;
        }
        const total = this.siswaList.reduce((sum, siswa) => sum + siswa.nilai, 0);
        return (total / this.siswaList.length).toFixed(2);
      }
    }
  };
  </script>
  