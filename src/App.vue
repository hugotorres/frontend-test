<template>
  <div id="app">
    <section class="  main-image">
      <div class="container">
        <div>
          <Menu></Menu>
        </div>
        <MainVote></MainVote>
      </div>
      <div class="row">
        <div class="text-one col-sm-4">CLOSING IN</div>
        <div class="text-two col-sm-8">22 days</div>
      </div>
    </section>
    <section class="container body">
      <div class="gray-p row">
        <div class="col-sm-2">
          <div class="top">Speak out. Be heard.</div>
          <div class="bottom">Be counted</div>
        </div>
        <div class="col-sm-10">
          <div class="right">
            Rule of Thumb is a crowd sourced court of public opinion where
            anyone and everyone can speak out and speak freely. It’s easy: You
            share your opinion, we analyze and put the data in a public report.
          </div>
        </div>
      </div>
      <h3>Votes</h3>
      <div class="boxes row" >
        <box
          v-for="character in characters" v-bind:key="character.id"
          :image=character.image
          :title=character.title
          :text=character.text
          :upvote=character.up
          :category=character.category
          :downvote=character.down
        ></box>
      </div>
    </section>
    <section id="pre-footer" class="container">
      <div>
        Is there anyone else you would want us to add?
        <a href="#"  class="submit">Submit a Name</a>
      </div>
    </section>
    <footer>
      footer
    </footer>
  </div>
</template>

<script lang="ts">
import { Component, Vue } from "vue-property-decorator";
import HelloWorld from "./components/HelloWorld.vue";
import Menu from "./components/Menu.vue";
import MainVote from "./components/MainVote.vue";
import Box from "./components/Box.vue";
import axios from "axios";

@Component({
  components: {
    HelloWorld,
    Menu,
    MainVote,
    Box
  }
})
export default class App extends Vue {
  characters = [];
  mounted() {
    axios({ method: "GET", url: "http://localhost:3000/character" }).then(
      result => {
        this.characters = result.data;
      },
      error => {
        alert(error);
      }
    );
  }
  updateVote(id:string) {
    alert(id);
  }
}
</script>

<style lang="scss">
#app {
  font-family: "Lato", sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  .right{
    padding-top: 6px;
    font-size: 16px;
    text-align: left;
  }
  .bottom {
    font-size: 29px;
    font-weight: bold;
}
  .body{
    h3{
      text-align:left;
    }
  }
  #pre-footer{ 
    font-size:18px;
    margin-top:30px; 
      
     div {
    
      font-size: 27px;
      padding: 10px 20px;
      text-align:left;
      background: url("assets/crowd.png");
      background-position:center;
      background-color: rgba(255,255,255,0.7);
      background-blend-mode: lighten;
      }
      .submit{
        border:thin solid black;
        padding:5px 20px;
        text-align:right;
        float:right;
        margin-top: -5px;
      }
  }
  .boxes {
    color: black;
  }

  .gray-p {
    margin-top: 30px;
    background: #ebebeb;
    padding: 10px;
    margin-right: 0px;
    margin-left: 0px;
    margin-bottom: 30px;
  }
}
.main-image {
  background: url("assets/pope.png");
  height: auto;
  color: white;
  background-size: cover;
  background-repeat: no-repeat;
  .row {
    margin-left: 0px;
    margin-right: 0px;
  }
  .text-one {
    background: #8080805e;
    height: 50px;
    text-align: right;
    padding: 13px;
  }
  .text-two {
    background: #ffffff73;
    height: 50px;
    color: rgba(70, 70, 70, 255);
    text-align: left;
    font-size: 32px;
  }
}
</style>
