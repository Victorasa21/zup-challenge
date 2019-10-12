<template>
  <div>
    <h1>{{titulo}}</h1>
    <div class="sideMenu-ContainerUsuario">
      <sideMenu></sideMenu>
      <Container-Usuario :pessoa="pessoa"></Container-Usuario>
    </div>
  </div>
</template>

<script>
import Usuario from "./Components/Shared/Usuario.vue";
import SideMenu from "./Components/Shared/SideMenu.vue";
export default {
  components: {
    "Container-Usuario": Usuario,
    SideMenu: SideMenu
  },
  data() {
    return {
      titulo: "Cadastro de pessoa",
      pessoa: []
    };
  },
  created() {
    this.$http
      .get("https://randomuser.me/api/?results=10")
      .then(res => res.json())
      .then(pessoa => (this.pessoa = pessoa.results));
  }
};
</script>

<style>
.circle {
  background-color: #aaa;
  border-radius: 50%;
  width: 10%;
  height: 10%;
  overflow: hidden;
  position: relative;
}

.circle img {
  position: absolute;
  bottom: 0;
  width: 100%;
}

.sideMenu-ContainerUsuario{
  display: flex;
  flex-direction: row;
}
</style>
