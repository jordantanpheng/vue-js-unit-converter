<template>
  <div>
    <div>
	  <h1>Unit Converter</h1>
	  Base Unit: <input v-model="baseunit" placeholder="Enter base unit name">
	  <br><br>
    </div>
    <h3>Add new conversion unit</h3>
    <new-conversion-unit @added="addnewUnit($event)"></new-conversion-unit>
	<h3>Values</h3>
	<values-list :list="units"></values-list>
  </div>
</template>
 
<script>
  import ValuesList from "./ValuesList.vue";
  import NewConversionUnit from "./NewConversionUnit.vue";
  export default {
    components: {NewConversionUnit, ValuesList},
    data() {
      return {
	    baseunit: "",
	    units: []
	  };
    },
    methods: {
      addnewUnit(newUnit) {
        this.units.push(newUnit);
      }
    }
  };
</script>