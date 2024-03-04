Vue.component("fiche-produit", {
  template: `
    <div class="col-3">
        <p class="jumbotron"> {{ nom }} <br>
            <button v-on:click="passerCommande(nom)" v-if="role == 'commande'" >Commander !</button>
            </p>
            </div>`,
  props: ["nom", "role"],
  methods: {
    passerCommande: function (produit) {
      this.$emit("commande-passee", produit);
    },
  },
});
const app = new Vue({
  router: "#app",
  data: {
    user: "Adrien",
    produits: ["Ultimate", "Course d'orientation", "Cyclisme", "Roller"],
    commandes: [],
    affichage: "display-4",
  },
  methods: {
    commander: function (produit) {
      // console.log(produit)
      this.commandes.push(produit);
    },
  },
}).$mount('#app');
