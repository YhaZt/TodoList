<script setup>
import WelcomeItem from './WelcomeItem.vue'
import DocumentationIcon from './icons/IconDocumentation.vue'
import ToolingIcon from './icons/IconTooling.vue'
import EcosystemIcon from './icons/IconEcosystem.vue'
import CommunityIcon from './icons/IconCommunity.vue'
import SupportIcon from './icons/IconSupport.vue'
</script>

<template>
<div>
  <h1 class = "h1">TODO List</h1>
  <br>
  <table style="width:100%">
    <thead>
    <tr>
      <td>Title</td>
      <td>Description</td>
      <td>Status</td>
      <td>Action</td>
    </tr>
  </thead>
  <tbody>

<tr  v-for="todo in todos" :key="todo.id">
  <td>{{todo.title}}</td>
  <td>{{todo.description}}</td>
  <td>{{todo.status}}</td>
  <td>{{todo.action}}</td>
</tr>

  </tbody>
  </table>
</div>
</template>
<script>
import axios from 'axios';

export default {
  data() {
    return {
      users: [],
    };
  },
  created() {
    axios.get('http:127.0.0.1:8080/api/index')
      .then(response => {
        this.users = response.data;
      })
      .catch(error => {
        console.log(error);
      });
  },
};
</script>