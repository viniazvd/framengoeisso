<template>
  <div>
    <div>
      <label>Nome</label>
      <input v-model="form.name" placeholder="Digite o nome" />
    </div>

    <div>
      <label>Time</label>
      <input v-model="form.team" placeholder="Digite o seu time" />
    </div>

    <div>
      <label>Sekisualidade</label>
      <input
        v-model="form.sekisuality"
        placeholder="Digite a sua sekisualidade"
      />
    </div>

    <button @click="addUser()">Cadastrar</button>

    <div v-for="(user, index) in users" :key="index">
      <p>Nome: {{ user.name }}</p>
      <p>Time: {{ user.team }}</p>
      <p>Sekisualids: {{ user.sekisuality }}</p>
      <hr />
    </div>
  </div>
</template>

<script lang="ts" setup>
import { ref } from "vue";

interface User {
  name: string;
  team: string;
  sekisuality: string;
}

const form = ref<User>({
  name: "",
  team: "",
  sekisuality: "",
});

const users = ref<User[]>([]);

function addUser() {
  users.value.push(form.value);
}
</script>
