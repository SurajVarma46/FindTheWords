<template>
  <v-layout justify-center class="main-container">
    <v-flex xs12 sm6 md4 lg4 xl4 class="inputs-container">
      <v-subheader>Enter number of rows:</v-subheader>

      <v-text-field v-model="rows" label="Rows" outline></v-text-field>
      <v-subheader>Enter number of columns:</v-subheader>

      <v-text-field v-model="cols" label="Columns" outline></v-text-field>
      <v-subheader>Choose the difficulty level:</v-subheader>
      <v-radio-group v-model="diff" row>
        <v-radio label="Easy" value="1"></v-radio>
        <v-radio label="Medium" value="2"></v-radio>
        <v-radio label="Hard" value="3"></v-radio>
      </v-radio-group>

      <v-subheader>Choose the directions of words:</v-subheader>
      <v-checkbox v-model="dir" label="Left-Right" value="1"></v-checkbox>
      <v-checkbox v-model="dir" label="Right-left" value="2"></v-checkbox>
      <v-checkbox v-model="dir" label="Top-Bottom" value="3"></v-checkbox>
      <v-checkbox v-model="dir" label="Bottom-Top" value="4"></v-checkbox>
      <v-checkbox v-model="dir" label="Diagonal-Left-Top-Bottom" value="5"></v-checkbox>
      <v-checkbox v-model="dir" label="Diagonal-Left-Bottom-Top" value="6"></v-checkbox>
      <v-checkbox v-model="dir" label="Diagonal-Right-Top-Bottom" value="7"></v-checkbox>
      <v-checkbox v-model="dir" label="Diagonal-Right-Bottom-Top" value="8"></v-checkbox>
      <div class="text-xs-center">
        <v-btn round color="green" dark @click="genGrid">Generate Grid</v-btn>
      </div>
    </v-flex>
    <v-flex xs12 sm6 md8 lg8 xl8 class="board-container">
      <table>
        <tr v-for="(row,index) in puzzle" :key="index">
          <td v-for="(col,index2) in row" :key="index2">{{col}}</td>
        </tr>
      </table>
    </v-flex>
  </v-layout>
</template>

<script>
export default {
  data: function() {
    return {
      rows: 10,
      cols: 10,
      diff: 1,
      dir: 1,
      words: [
        "hello",
        "clear",
        "cost",
        "hostile",
        "game",
        "crossword",
        "similar",
        "shameful",
        "response",
        "apple"
      ],
      puzzle: []
    };
  },
  methods: {
    genGrid() {
      const nOfWords = this.words.length;
      let puzzle = [];
      for (let i = 0; i < this.rows; i++) {
        puzzle[i] = [];
        for (let j = 0; j < this.cols; j++) {
          puzzle[i][j] = "*";
        }
      }
      this.puzzle = puzzle;
    }
  },
  mounted() {
    this.genGrid();
  }
};
</script>


<style>
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

table,
td {
  border: 1px solid black;
  border-collapse: collapse;
}

td {
  padding: 15px;
  text-align: center;
}

table {
  width: 100%;
}
</style>