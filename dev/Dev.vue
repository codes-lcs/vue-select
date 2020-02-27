<template>
  <div id="app">
    <sandbox hide-help v-slot="config">
      <v-select v-bind="config" />
      <hr/>
      Add Action Button
      <v-select v-model="selected" v-bind="config" :actionButton="actionButton"/>
    </sandbox>
  </div>
</template>

<script>
import vSelect from '../src/components/Select';
import Sandbox from '../docs/.vuepress/components/Sandbox';
// import countries from '../docs/.vuepress/data/countryCodes';
// import books from '../docs/.vuepress/data/books';

export default {
  components: {Sandbox, vSelect},
  data() {
    return {
      selected:null,
      // actionButton: {
      //   classIcon:'glyphicon glyphicon-plus', 
      //   title:'New', 
      //   action:this.clickNew
      // }
    }
  },
  computed: {
    actionButton() {
      if(this.selected === null){
        return {
          classIcon:'glyphicon glyphicon-plus', 
          title:'New', 
          action:this.clickNew
        }
      }

      if(this.selected !== null){
        return {
          classIcon:'glyphicon glyphicon-pencil', 
          title:'Edit', 
          action:this.clickEdit
        }
      }
    }
  },
  methods: {
    clickNew: function() {
      let $this = this;
      alert('Test click button New: ');
    },
    clickEdit: function() {
      let $this = this;
      alert('Test click button Edit: ');
    }
  }
};
</script>

<style>
  html,
  body {
    margin: 0;
    height: 100%;
    font-family: -apple-system, sans-serif;
  }

  #app {
    height: 100%;
  }

  hr {
    border: none;
    border-bottom: 1px solid #cacaca;
    margin-bottom: 1em;
    padding-top: 1em;
    width: 90%;
  }
</style>
