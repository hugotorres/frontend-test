<template>
  <div class="container-vote-box">
    <div class="content">
      <p>whats your opinion on</p>
      <h4>POPE FRANCIS</h4>
      <p>
        He’s talking tough on clergy sexual abuse, but is he just another papal
        pervert protector? (thumbs down) or a true pedophile punishing pontiff?
        (thumbs up)
      </p>
      <p class="more-info">
        <img src="../assets/w.png" alt="wiki" />More information
      </p>
      <p>What’s Your Verdict?</p>
    </div>
    <div class="row buttons">
      <div class="col-6 vote-up">
        <img src="../assets/hand.png" alt="vote-up" />
      </div>
      <div class="col-6 vote-down">
        <img src="../assets/hand.png" alt="vote-down" />
      </div>
    </div>
  </div>
</template>
<style scoped lang="scss">
.vote-up {
  height: 60px;
  background-color: #2cbbb3;
  padding: 10px;
}
.vote-down {
  height: 60px;
  background-color: #fcb230;
  padding: 10px;
  img {
    rotate: 180deg;
  }
}
.container-vote-box {
  background: #8585857a;
  width: 400px;

  overflow: hidden;
  backdrop-filter: blur(13px);
  margin-top: 84px;
  margin-bottom: 50px;
  .more-info {
    margin-bottom: 0.5rem;
    font-size: 13px;
  }

  .vote-up {
    height: 60px;
    background-color: #2cbbb3;
    cursor: pointer;
  }
  .vote-down {
    height: 60px;
    background-color: #fcb230;
    cursor: pointer;
  }
  span {
    font-size: 16px;
    color: rgba(255, 255, 255, 255);
    text-align: left;
  }
  .content {
    padding: 28px;
    color: white;
    text-align: left;
    padding-bottom: 0px;
    h4 {
      font-size: 48px;
    }
  }
}
</style>
<script lang="ts">
import { Component, Prop, Vue } from "vue-property-decorator";
@Component
export default class MainVote extends Vue {}
</script>
