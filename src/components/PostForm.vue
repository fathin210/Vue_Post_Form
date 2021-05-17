<template>
  <form class="wrap" @submit.prevent="submit">
    <input type="text" v-model="mahasiswa.nama" placeholder="Nama" />
    <input type="text" v-model="mahasiswa.nim" placeholder="NIM" />
    <button type="submit">Submit</button>
  </form>
</template>

<script>
import axios from "axios";

export default {
  name: "PostForm",
  data() {
    return {
      mahasiswa: {
        nama: "",
        nim: "",
      },
    };
  },

  methods: {
    submit() {
      axios
        .post("https://jsonplaceholder.typicode.com/posts", {
          nama: this.mahasiswa.nama,
          nim: this.mahasiswa.nim,
        })
        .then((res) => console.log(res.data))
        .catch((err) => console.log(err));

      // Ini kalo gunain fetch
      //   fetch("https://jsonplaceholder.typicode.com/posts", {
      //     method: "POST",
      //     headers: { "Content-Type": "application/json" },
      //     body: JSON.stringify({
      //       nama: this.mahasiswa.nama,
      //       nim: this.mahasiswa.nim,
      //     }),
      //   })
      //     .then((res) => console.log(res.json()))
      //     .catch((err) => console.log(err));
      // },
    },
  },
};
</script>

<style scoped>
.wrap {
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  margin: 20px;
}

input {
  margin-bottom: 10px;
  padding: 10px;
}

button {
  padding: 10px;
  background-color: midnightblue;
  color: white;
}
</style>