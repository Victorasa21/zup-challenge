<template>
  <div class="all-users">
    <div class="container-usuario" v-for="pessoa of pessoa">
      <img class="circle" :src="pessoa.picture.medium" alt="picture" />
      <h1>{{pessoa.name.first}}</h1>
      <h1>{{pessoa.email}}</h1>
      <h1>{{pessoa.phone}}</h1>
      <h1>{{pessoa.city}}</h1>
      <div class="image-options">
        <img src="../../Public/lixeira/lixeira.png" alt="lixeira" />
        <img src="../../Public/selectAll/selectAll.png" alt="selectAll" />
        <img src="../../Public/done/done.png" alt="done" />
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: ["pessoa"]
};
</script>

<style>
.container-usuario {
  display: flex;
  align-items: center;
  justify-content: space-around;
  flex-direction: row;
  border: 2px solid palegreen;
}
.container-usuario h1 {
  font-size: 1em;
  margin: 30px;
  font-family: "Times New Roman", Times, serif;
  border-color: aquamarine;
}

.circle {
  background-color: #aaa;
  border-radius: 50%;
  width: 40px;
  height: 40px;
  overflow: hidden;
  position: relative;
}

.circle img {
  position: absolute;
  bottom: 0;
  width: 100%;
}
.image-options {
  height: 20px;
  float:right;
}


</style>
