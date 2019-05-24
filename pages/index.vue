<template>
  <section class="container">
    <div id="rows">
      <v-container fluid>
        <v-layout row wrap>
          <v-flex xs12 sm12>
            <v-subheader>Enter number of rows</v-subheader>
            <v-text-field label="Rows" value="10" outline></v-text-field>
          </v-flex>
        </v-layout>
      </v-container>
    </div>
    <div id="cols">
      <v-container fluid>
        <v-layout row wrap>
          <v-flex xs12 sm12>
            <v-subheader>Enter number of columns</v-subheader>
            <v-text-field label="Columns" value="10" outline></v-text-field>
          </v-flex>
        </v-layout>
      </v-container>
    </div>
    <div id="difficulty">
      <v-container fluid>
        <v-layout row wrap>
          <v-flex xs12 sm12>
            <v-subheader>Choose the difficulty level</v-subheader>
            <v-radio-group v-model="difficulty" row>
              <v-radio label="Easy" value="1"></v-radio>
              <v-radio label="Medium" value="2"></v-radio>
              <v-radio label="Hard" value="3"></v-radio>
            </v-radio-group>
          </v-flex>
        </v-layout>
      </v-container>
    </div>
    <div id="modofwords">
      <v-container fluid>
        <v-layout>
          <v-flex xs12 sm12>
            <v-subheader>Select all the models of words</v-subheader>
            <v-checkbox v-model="modofwords" label="Left-Right" value="1"></v-checkbox>
            <v-checkbox v-model="modofwords" label="Right-left" value="2"></v-checkbox>
            <v-checkbox v-model="modofwords" label="Top-Bottom" value="3"></v-checkbox>
            <v-checkbox v-model="modofwords" label="Bottom-Top" value="4"></v-checkbox>
            <v-checkbox v-model="modofwords" label="Diagonal-Left-Top-Bottom" value="5"></v-checkbox>
            <v-checkbox v-model="modofwords" label="Diagonal-Left-Bottom-Top" value="6"></v-checkbox>
            <v-checkbox v-model="modofwords" label="Diagonal-Right-Top-Bottom" value="7"></v-checkbox>
            <v-checkbox v-model="modofwords" label="Diagonal-Right-Bottom-Top" value="8"></v-checkbox>
          </v-flex>
        </v-layout>
      </v-container>
    </div>
  </section>
</template>

<script>
export default {};
</script>


<style>
.container {
  margin: 0 auto;
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}

.title {
  font-family: "Quicksand", "Source Sans Pro", -apple-system, BlinkMacSystemFont,
    "Segoe UI", Roboto, "Helvetica Neue", Arial, sans-serif;
  display: block;
  font-weight: 300;
  font-size: 100px;
  color: #35495e;
  letter-spacing: 1px;
}

.inputs {
  font-family: "Source Sans Pro", "Arial";
  display: block;
  font-weight: 50;
  font-size: 16px;
  color: black;
}
.links {
  padding-top: 15px;
}
</style>
