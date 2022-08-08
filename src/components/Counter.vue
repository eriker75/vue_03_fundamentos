<template>
  <h2>{{customTitle}}</h2>
  <p>{{counter}} <sup>{{sup}}</sup> = {{squareCounter}}</p>
  <div>
    <button @click="addValToCounter(-1)">-1</button>
    <button @click="resetCounter()">Reset</button>
    <button @click="addValToCounter(1)">+1</button>
  </div>
</template>

<script>
export default {
  name: 'CounterComponent',
  props: {
    title: String,
    superv: {
      type: Number,
      required : true,
      default: 2,
      validator(value){
        return value>=1;
      }
    },
    defcounter: {
      type: Number,
      default: 10,
      required: true
    }
  },  
  data() {
    return {
      counter: this.defcounter,
      sup: this.superv,
    }
  },
  computed:{
    squareCounter(){
      return Math.pow(this.counter,this.sup);
    },
    customTitle(){
      return this.title  || 'Counter';
    }
  },
  methods: {
    addValToCounter(val = 1){
      this.counter = this.counter + val;
    },
    resetCounter(){
      this.counter = 0;
    }
  }
}
</script>

<style scoped>
  button{
    background-color: #64B687;
    border-radius: 5px;
    border: 1px solid white;
    color: white;
    cursor: pointer;
    margin: 0 5px;
    padding: 5px 15px;
    transition: 0.3s ease-in-out;
    font-weight: bold;
  }
  button:hover {
    background-color: #5aa67b;
    transition: 0.3s ease-in-out;
  }
</style>