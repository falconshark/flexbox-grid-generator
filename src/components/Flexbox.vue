<template>
  <div class="container">
    <label for="box-num">Box numbers in row:</label>
    <select id="box-num" v-model="boxNum"  @change="selectNum">
      <option :value="1">1</option>
      <option :value="2">2</option>
      <option :value="3">3</option>
      <option :value="4">4</option>
      <option :value="5">5</option>
      <option :value="6">6</option>
    </select>
    <div class="row">
      <div :class="boxClass" v-for="(n, index) in boxNum">
        Hello World
      </div>
    </div>
    <div class="code">
      <div class="form-group">
        <label for="code">CSS Code:</label>
        <textarea class="form-control" id="code" rows="7" readonly="readonly">
          {{code}}
        </textarea>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Flexbox',
  data () {
    return {
      boxNum: 1,
      boxClass: 'grid-box col-md-12',
      code:
      `.col-md-12 {
        -webkit-box-flex: 0;
        -ms-flex: 0 0 100%;
        flex: 0 0 100%;
        max-width: 100%;
      }`,
    }
  },

  methods:{
    selectNum(){
      const boxNum = this.boxNum;
      switch(boxNum){
        case 1:
        this.boxClass = 'grid-box col-md-12';
        this.code =
        `.col-md-12 {
          -webkit-box-flex: 0;
          -ms-flex: 0 0 100%;
          flex: 0 0 100%;
          max-width: 100%;
        }`;
        break;

        case 2:
        this.boxClass = 'grid-box col-md-6';
        this.code =
        `.col-md-6 {
          -webkit-box-flex: 0;
          -ms-flex: 0 0 50%;
          flex: 0 0 50%;
          max-width: 50%;
        }`;
        break;

        case 3:
        this.boxClass = 'grid-box col-md-4';
        this.code = `.col-md-4 {
          -webkit-box-flex: 0;
          -ms-flex: 0 0 33.333333%;
          flex: 0 0 33.333333%;
          max-width: 33.333333%;
        }`;
        break;

        case 4:
        this.boxClass = 'grid-box col-md-3';
        this.code = `.col-md-3 {
          -webkit-box-flex: 0;
          -ms-flex: 0 0 25%;
          flex: 0 0 25%;
          max-width: 25%;
        }`;
        break;

        case 5:
        this.boxClass = 'grid-box col-md';
        this.code = `.col-md {
          -ms-flex-preferred-size: 0;
          flex-basis: 0;
          -webkit-box-flex: 1;
          -ms-flex-positive: 1;
          flex-grow: 1;
          max-width: 100%;
        }`;
        break;

        case 6:
        this.boxClass = 'grid-box col-md-2';
        this.code = `.col-md-2 {
          -webkit-box-flex: 0;
          -ms-flex: 0 0 16.666667%;
          flex: 0 0 16.666667%;
          max-width: 16.666667%;
        }`;
        break;
      }
    },
  },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.container{
  margin-top: 1em;
}
.row{
  border: 1px solid #2C3E50;
  margin-top: 1em;
  padding: 2em;
  min-height: 150px;
}
.grid-box{
  border: 1px solid #2C3E50;
  padding: 1em;
  display: flex;
  align-items: center;
  justify-content: center;
  min-height: 150px;
}
.code{
  margin-top: 60px;
}
</style>
