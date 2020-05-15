<template>
  <div>
    <form @submit.prevent="add()">
	<div class="form-group">
      <label>Conversion unit name</label>
      <input type="text" class="form-control" placeholder="Enter conversion unit name" v-model="newUnit.name">
      <label>Base multiplier</label>
      <input type="number" step="0.0001" class="form-control" placeholder="Enter base multiplier" v-model="newUnit.multiplier">
	  <br>
      <button class="btn btn-primary mb-2">Add</button>
	</div>
    </form>
  </div>
</template>

<script>
  export default {
    data() {
      return {newUnit: {}};
    },
    methods: {
      add() {
        this.$emit('added', this.newUnit);
        this.newUnit = {};
      }
    }
  };
</script> 