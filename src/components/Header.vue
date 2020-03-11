<template>
<div>
    <div>
      <b-navbar toggleable="lg" type="dark" variant="info">
        <b-navbar-brand href="#">Search-Beer</b-navbar-brand>

        <b-navbar-toggle target="nav-collapse"></b-navbar-toggle>

        <b-collapse id="nav-collapse" is-nav>
          <b-navbar-nav>
            <b-nav-item href="#">Grupo</b-nav-item>
            <b-nav-item href="#" disabled>Contato</b-nav-item>
          </b-navbar-nav>

          <!-- Right aligned nav items -->
          <b-navbar-nav class="ml-auto">
            <b-nav-form>
              <b-form-input size="sm" class="mr-sm-2" placeholder="Search"></b-form-input>
              <b-button size="sm" class="my-2 my-sm-0" type="submit">Pesquisar</b-button>
            </b-nav-form>

            <b-nav-item-dropdown text="Linguagem" right>
              <b-dropdown-item href="#">PT-BR</b-dropdown-item>
              <b-dropdown-item href="#">ES</b-dropdown-item>
              <b-dropdown-item href="#">RU</b-dropdown-item>
              <b-dropdown-item href="#">FA</b-dropdown-item>
            </b-nav-item-dropdown>

            <b-nav-item-dropdown right>
              <!-- Using 'button-content' slot -->
              <template v-slot:button-content>
                <em>Login</em>
              </template>
              <b-dropdown-item href="#">Logar</b-dropdown-item>
              <b-dropdown-item href="#">Sair</b-dropdown-item>
            </b-nav-item-dropdown>
          </b-navbar-nav>
        </b-collapse>
      </b-navbar>
    </div>

    <h1>Bem vindo as {{title}}</h1>

    <section class="fundo">
      <div id="action">
        <div id="keg">
          <div id="pipe-handle"></div>
          <div id="pipe"></div>
          <div id="pipe-front"></div>
        </div>

        <div class="glass">
          <div class="beer"></div>
          <div class="handle">
            <div class="top-right"></div>
            <div class="bottom-right"></div>
          </div>
          <div class="front-glass"></div>
        </div>
      </div>
    </section>
</div>


</template>

<script>
export default {
  name: "Header",
}

</script>

<style>
h1 {
  display: inline-block;
  margin-top: 50px;
  color: rgb(221, 169, 0);
  border-top: solid 5px rgb(221, 169, 0);
  border-bottom: solid 5px rgb(221, 169, 0);
  transform: skew(0, 0deg);
}
</style>