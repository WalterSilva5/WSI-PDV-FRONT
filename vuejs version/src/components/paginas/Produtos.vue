<template>
  <div class="col-12 container-fluid corpo-margem wsi-fade">
    <header-top>
      <div>
        <button
          class="btn wsi-btn-secondary wsi-btn-menu-shadow"
          data-toggle="modal"
          data-target="#modalVendas"
          @click="abrirModalCadastroProduto(true)"
        >
          CADASTRAR
        </button>
      </div> </header-top
    ><modal-cadastro-produto
      @abrirModalCadastroProduto="abrirModalCadastroProduto"
      class="modal-dialogo wsi-fade"
      v-show="modalCadastroProdutoAtivo"
    />
  </div>
  <div>
    <tabela-de-produtos />
  </div>
</template>

<script>
import HeaderTop from "./components/HeaderTop.vue";
import ModalCadastroProduto from "./produtos/ModalCadastroDeProduto.vue";
import TabelaDeProdutos from "./produtos/TabelaDeProdutos.vue";
export default {
  components: {
    HeaderTop,
    ModalCadastroProduto,
    TabelaDeProdutos,
  },
  data() {
    return {
      modalCadastroProdutoAtivo: false,
    };
  },
  methods: {
    abrirModalCadastroProduto(state = false) {
      this.modalCadastroProdutoAtivo = state;
    },
  }
};
</script>

<style lang="scss" scoped>
td {
  overflow: auto;
}
</style>
