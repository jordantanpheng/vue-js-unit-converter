<template>
  <div>
    Value to convert: <input v-model.number="valuetoconvert" step="0.1" type="number" placeholder="Enter value">
	<br><br>
    <ul>
        <li v-for="unit in list">
           {{ valuetoconvert * unit.multiplier }} {{ unit.name }} 
        </li>
    </ul>
  </div>
</template>

<script>
  export default {
    data() {
		return {valuetoconvert : 1}
    },
    props: ['list']
  };
</script> 