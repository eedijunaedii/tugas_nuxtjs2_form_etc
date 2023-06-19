<template>
    <div>
      <h2>Form Siswa</h2>
      <form @submit.prevent="submitForm">
        <div>
          <label for="induk">No Induk Siswa:</label>
          <input type="text" id="induk" v-model="siswa.induk">
        </div>
        <div>
          <label for="nama">Nama Siswa:</label>
          <input type="text" id="nama" v-model="siswa.nama">
        </div>
        <div>
          <label for="nilai">Nilai Tugas:</label>
          <input type="number" id="nilai" v-model="siswa.nilai">
        </div>
        <button type="submit">Tambah Siswa</button>
      </form>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        siswa: {
          induk: '',
          nama: '',
          nilai: 0
        }
      };
    },
    methods: {
      submitForm() {
        this.$emit('siswa-added', this.siswa);
        this.siswa = {
          induk: '',
          nama: '',
          nilai: 0
        };
      }
    }
  };
  </script>
  