<template>
  <v-layout justify-center class="main-container">
    <v-flex xs12 sm6 md4 lg4 xl4 class="inputs-container">
      <v-subheader>Enter number of rows:</v-subheader>

      <v-text-field label="Rows" value="10" outline></v-text-field>
      <v-subheader>Enter number of columns:</v-subheader>

      <v-text-field label="Columns" value="10" outline></v-text-field>
      <v-subheader>Choose the difficulty level:</v-subheader>
      <v-radio-group row>
        <v-radio label="Easy" value="1"></v-radio>
        <v-radio label="Medium" value="2"></v-radio>
        <v-radio label="Hard" value="3"></v-radio>
      </v-radio-group>

      <v-subheader>Choose the directions of words:</v-subheader>
      <v-checkbox label="Left-Right" value="1"></v-checkbox>
      <v-checkbox label="Right-left" value="2"></v-checkbox>
      <v-checkbox label="Top-Bottom" value="3"></v-checkbox>
      <v-checkbox label="Bottom-Top" value="4"></v-checkbox>
      <v-checkbox label="Diagonal-Left-Top-Bottom" value="5"></v-checkbox>
      <v-checkbox label="Diagonal-Left-Bottom-Top" value="6"></v-checkbox>
      <v-checkbox label="Diagonal-Right-Top-Bottom" value="7"></v-checkbox>
      <v-checkbox label="Diagonal-Right-Bottom-Top" value="8"></v-checkbox>
    </v-flex>
    <v-flex xs12 sm6 md8 lg8 xl8 class="board-container"></v-flex>
  </v-layout>
</template>

<script>
export default {};
</script>


<style>
.main-container {
}

.inputs-container {
  opacity: 0.8;
  padding: 1rem;
}

.board-container {
  border: 1px solid #eee;
  background: #f8f8f8;
  margin: 1rem;
  border-radius: 0.25rem;
}
</style>