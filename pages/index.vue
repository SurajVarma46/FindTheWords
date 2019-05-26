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
function generate_random_char() {
  let random_char = "";
  let random_ascii;
  random_ascii = Math.floor(Math.random() * 25 + 97);
  random_char = String.fromCharCode(random_ascii);
  return random_char;
}
function getRandomInt(max) {
  return Math.floor(Math.random() * Math.floor(max));
}
export default {
  data: function() {
    return {
      rows: 12,
      cols: 12,
      diff: 1,
      dir: 1,
      words: [
        "HELLO",
        "CLEARANCE",
        "ORANGE",
        "BANANA",
        "GAMES",
        "CROSSWORD",
        "SIMILAR",
        "SHAMEFUL",
        "RESPONSE",
        "APPLE",
        "YELLOW",
        "PURPLE"
      ],
      puzzle: []
    };
  },
  methods: {
    genGrid() {
      const nOfWords = this.words.length;
      this.words.sort(function(a, b) {
        return b.length - a.length;
      });
      let puzzle = [];
      for (let i = 0; i < this.rows; i++) {
        puzzle[i] = [];
        for (let j = 0; j < this.cols; j++) {
          puzzle[i][j] = "";
        }
      }
      let step = 0;
      while (step < this.words.length) {
        this.words[step] = this.words[step]
          .split("")
          .reverse()
          .join("");
        step += 2;
      }

      for (let m = 0, i = 3; m < this.words.length; m = m + 2, i = i + 2) {
        let j = getRandomInt(this.cols - this.words[m].length + 1);
        for (let k = 0; k < this.words[m].length; k++, j++) {
          if (i >= this.rows) {
            i = 0;
          }
          if (puzzle[i][j] == "" || puzzle[i][j] == this.words[m][k]) {
            puzzle[i][j] = this.words[m][k];
          }
        }
      }
      for (let m = 1, i = 3; m < this.words.length; m = m + 2, i = i + 2) {
        let j = getRandomInt(this.rows - this.words[m].length + 1);
        for (let k = 0; k < this.words[m].length; k++, j++) {
          if (i >= this.cols) {
            i = 0;
          }
          if (puzzle[j][i] == "" || puzzle[j][i] == this.words[m][k]) {
            puzzle[j][i] = this.words[m][k];
          }
        }
      }

      /*
        for (let k = this.words[i].length; k < this.cols; k++) {
          puzzle[i][k] = generate_random_char();
        }
      */
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