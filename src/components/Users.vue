<template>
  <div class="container">
    <table class="table">
      <thead>
        <tr>
          <th scope="col">ID</th>
          <th scope="col">Name</th>
          <th scope="col">Username</th>
          <th scope="col">Email</th>
          <th scope="col">Website</th>
          <th scope="col">City</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="user in users" :key="user.id">
          <th scope="row">{{ user.id }}</th>
          <td>{{ user.name }}</td>
          <td>{{ user.username }}</td>
          <td>{{ user.email }}</td>
          <td>{{ user.website }}</td>
          <td>{{ user.address.city }}</td>
        </tr>
      </tbody>
    </table>
  </div>
</template>
<script>
import axios from "axios";
export default {
  name: "UserList",
  data() {
    return {
      users: null,
    };
  },
  created: function () {
    axios.get("https://jsonplaceholder.typicode.com/users").then((res) => {
      this.users = res.data;
      console.log(this.users);
    });
  },
};
</script>
<style></style>
<!-- Apı ulaşabilmem için url request(istek) atmam lazım -->
<!--Vue tarafında axios kullanıcaz-->
<!--Url ile Axiosta  request işlemi gerçekleştirip statemde datalarımı tutup componentin üzerinde listeliyor olabilmem gerekiyor.-->
