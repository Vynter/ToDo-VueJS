<template>
  <tr>
    <th scope="row">{{ i + 1 }}</th>
    <td colspan="8">{{ task }}</td>
    <td class="justify-content-center align-items-center text-center">
      <button v-on:click="Done" class="btn btn-outline-danger">X</button>
    </td>
  </tr>
</template>

<script>
export default {
  name: "Tache",
  data() {
    return {};
  },
  props: ["Done", "i", "task"],
};
</script>

<style scoped>
tr > th {
  width: 20px !important;
}
</style>
