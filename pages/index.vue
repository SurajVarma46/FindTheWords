<template>
  <section>
    <div id="inputs">
      <v-container column>
        <v-layout column>
          <v-layout align-start row>
            <v-flex xs6 sm3>
              <v-subheader>Enter number of rows:</v-subheader>
              <br>
              <br>
              <v-subheader>Enter number of columns:</v-subheader>
              <br>
              <br>
              <v-subheader>Choose the difficulty level:</v-subheader>
            </v-flex>
            <v-flex xs10 sm5>
              <v-text-field label="Rows" value="10" outline></v-text-field>
              <v-text-field label="Columns" value="10" outline></v-text-field>
              <v-radio-group row>
                <v-radio label="Easy" value="1"></v-radio>
                <v-radio label="Medium" value="2"></v-radio>
                <v-radio label="Hard" value="3"></v-radio>
              </v-radio-group>
            </v-flex>
          </v-layout>
          <v-layout align-start row>
            <v-flex xs8 sm3>
              <v-subheader>Choose the directions of words:</v-subheader>
            </v-flex>
            <v-flex xs8 sm4>
              <v-checkbox label="Left-Right" value="1"></v-checkbox>
              <v-checkbox label="Right-left" value="2"></v-checkbox>
              <v-checkbox label="Top-Bottom" value="3"></v-checkbox>
              <v-checkbox label="Bottom-Top" value="4"></v-checkbox>
            </v-flex>
            <v-flex xs8 sm5>
              <v-checkbox label="Diagonal-Left-Top-Bottom" value="5"></v-checkbox>
              <v-checkbox label="Diagonal-Left-Bottom-Top" value="6"></v-checkbox>
              <v-checkbox label="Diagonal-Right-Top-Bottom" value="7"></v-checkbox>
              <v-checkbox label="Diagonal-Right-Bottom-Top" value="8"></v-checkbox>
            </v-flex>
          </v-layout>
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
