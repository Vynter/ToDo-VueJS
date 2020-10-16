<template>
  <div class="container">
    <h1 class=" mt-5 text-center">Liste des taches</h1>
    <!--  -->
    <form action="">
      <div class="form-group">
        <label class="font-weight-bold">Tache</label>
        <input
          v-model="inp"
          type="text"
          name="task"
          class="form-control badge-dark"
          placeholder="Saisissez votre tache..."
        />
      </div>
      <button v-on:click.prevent="AddTask" class="btn btn-dark">
        Ajouter
      </button>
    </form>
    <!--  -->
    <table v-if="dispo" class="table table-bordered table-dark mt-5 ">
      <thead>
        <tr>
          <th scope="col" colspan="1">#</th>
          <th scope="col" colspan="8">Taches</th>
          <th scope="col" colspan="1">Action</th>
        </tr>
      </thead>
      <tbody>
        <Task
          v-for="(item, index) in tachesTab"
          v-bind:key="index"
          v-bind:task="item"
          v-bind:i="index"
          v-bind:Done="closethat"
          v-bind:id="index"
        ></Task>
      </tbody>
    </table>

    <!--  -->
  </div>
</template>

<script>
import Task from "./Tache.vue";

export default {
  name: "Contenu",
  data() {
    return {
      tachesTab: ["aze", "qsd"],
      dispo: true,
      inp: "",
    };
  },
  components: {
    Task,
  },
  methods: {
    closethat: function(e) {
      this.tachesTab.splice(e.target.parentNode.parentNode.id, 1);
      //   if (this.tachesTab.length >= 1) {
      //     this.dispo = true;
      //   }
    },
    AddTask: function() {
      this.tachesTab.push(this.inp);
      //   if (this.tachesTab.length === 0) {
      //     this.dispo = false;
      //   }
    },
  },

  watch: {
    tachesTab: function() {
      if (this.tachesTab.length === 0) {
        this.dispo = false;
      } else {
        this.dispo = true;
      }
    },
  },
};
</script>

<style scoped>
tr > th {
  width: 20px !important;
}
</style>
