<template>
  <div class="col-sm-6 voting-box">
    <div class="content mt-4 text-left" :style="{ backgroundImage: 'url(' + image + ')' }">
      <h3>{{ title }}</h3>
      <span>
        1 month ago
        <b>in {{category}}</b>
      </span>
      <p class="vote-text"  v-if="voting">{{ text }}</p>
      <div class="thanks"> <p class="vote-text"  v-if="!voting">Thanks for voting!</p></div>
      <div class="voting-buttons">
        <div v-if="voting">
          <div class="up" v-bind:class="{ active: selected===1 }"  v-on:click="setActive(1)">
            <img
              data-v-61c48ef3
              src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAACQAAAAlCAYAAAAqXEs9AAAB5UlEQVRYR83YTYhOURzH8e93QUlRNiRNavKyUZY2aBaaJpmNFWUhRVJKCgkbpCyU0ESSlK2GKU2JjZ2ssJmJvDZKCAtvyV9nemiiuc+dk+fOOftzfp/nufec//8eyRwRsRY4DywBHgPngLPqz8wlx6eZOzkiRoClf82/CmxRI3fdLFBEzAPeTRK6Vb3cNKgLeD5J6Ki6rGnQAuB1RegK9VEOKveRzQU+VARuUy81CVoMPK0IPKnubxLUD1yvCDyj7m4SdCVt74rAw+qxRkARsQh4AsysCNyoXmsKlA6/zW3C5qtvOg6KiF5guE3QiLo8BzOl0hERs4CHQHebsFPq3iZAp4E6O2eNerejoIjoAW7XLMZ3gKlU/B/AGDCoDhkRtyp+zZ5WzXoApMOw0+NAAlW1CquBDcC+Tkta6z+rA9pZY5v/L+/30kD3SwJ9BHpLAY0CPepYKaD0Dp5QD5YE+grMKQmUjp/ZJYGG1b4SQF+AIWCX+rYEUPo66VNfjbcfNUpHEyf1BXVHSaCb6vqSQIfU46WAbgCb1M8lgI6qRya2CtP9Ur8HFqrffqOmG5QcXerLUkD3gFUTL7jq/EPb23w253aLL4B1amo9/ow6oE/ARWAlMCM3vTUvXeEkwCAwoP5zpfMLzjPicGiSuqUAAAAASUVORK5CYII="
              alt="vote"
            />
          </div>
          <div class="down" v-bind:class="{ active: selected===2 }"  v-on:click="setActive(2)">
            <img
              data-v-61c48ef3
              src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAACQAAAAlCAYAAAAqXEs9AAAB5UlEQVRYR83YTYhOURzH8e93QUlRNiRNavKyUZY2aBaaJpmNFWUhRVJKCgkbpCyU0ESSlK2GKU2JjZ2ssJmJvDZKCAtvyV9nemiiuc+dk+fOOftzfp/nufec//8eyRwRsRY4DywBHgPngLPqz8wlx6eZOzkiRoClf82/CmxRI3fdLFBEzAPeTRK6Vb3cNKgLeD5J6Ki6rGnQAuB1RegK9VEOKveRzQU+VARuUy81CVoMPK0IPKnubxLUD1yvCDyj7m4SdCVt74rAw+qxRkARsQh4AsysCNyoXmsKlA6/zW3C5qtvOg6KiF5guE3QiLo8BzOl0hERs4CHQHebsFPq3iZAp4E6O2eNerejoIjoAW7XLMZ3gKlU/B/AGDCoDhkRtyp+zZ5WzXoApMOw0+NAAlW1CquBDcC+Tkta6z+rA9pZY5v/L+/30kD3SwJ9BHpLAY0CPepYKaD0Dp5QD5YE+grMKQmUjp/ZJYGG1b4SQF+AIWCX+rYEUPo66VNfjbcfNUpHEyf1BXVHSaCb6vqSQIfU46WAbgCb1M8lgI6qRya2CtP9Ur8HFqrffqOmG5QcXerLUkD3gFUTL7jq/EPb23w253aLL4B1amo9/ow6oE/ARWAlMCM3vTUvXeEkwCAwoP5zpfMLzjPicGiSuqUAAAAASUVORK5CYII="
              alt="vote"
            />
          </div>
          <div class="vote-link" v-on:click="voting = false">Vote</div>
        </div>
        <div class="vote-link" v-if="!voting" v-on:click="voting = true">Vote again</div>
      </div>

      <div class="rating">
        <div class="upvote float-left" v-bind:style="{width: upvote+'%'}">
          <img
            data-v-61c48ef3
            src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAACQAAAAlCAYAAAAqXEs9AAAB5UlEQVRYR83YTYhOURzH8e93QUlRNiRNavKyUZY2aBaaJpmNFWUhRVJKCgkbpCyU0ESSlK2GKU2JjZ2ssJmJvDZKCAtvyV9nemiiuc+dk+fOOftzfp/nufec//8eyRwRsRY4DywBHgPngLPqz8wlx6eZOzkiRoClf82/CmxRI3fdLFBEzAPeTRK6Vb3cNKgLeD5J6Ki6rGnQAuB1RegK9VEOKveRzQU+VARuUy81CVoMPK0IPKnubxLUD1yvCDyj7m4SdCVt74rAw+qxRkARsQh4AsysCNyoXmsKlA6/zW3C5qtvOg6KiF5guE3QiLo8BzOl0hERs4CHQHebsFPq3iZAp4E6O2eNerejoIjoAW7XLMZ3gKlU/B/AGDCoDhkRtyp+zZ5WzXoApMOw0+NAAlW1CquBDcC+Tkta6z+rA9pZY5v/L+/30kD3SwJ9BHpLAY0CPepYKaD0Dp5QD5YE+grMKQmUjp/ZJYGG1b4SQF+AIWCX+rYEUPo66VNfjbcfNUpHEyf1BXVHSaCb6vqSQIfU46WAbgCb1M8lgI6qRya2CtP9Ur8HFqrffqOmG5QcXerLUkD3gFUTL7jq/EPb23w253aLL4B1amo9/ow6oE/ARWAlMCM3vTUvXeEkwCAwoP5zpfMLzjPicGiSuqUAAAAASUVORK5CYII="
            alt="vote-up"
          />
          <div class="upvote-count">{{ upvote }}%</div>
        </div>
        <div class="downvote float-right" v-bind:style="{width: downvote+'%'}">
          <img
            data-v-61c48ef3
            src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAACQAAAAlCAYAAAAqXEs9AAAB5UlEQVRYR83YTYhOURzH8e93QUlRNiRNavKyUZY2aBaaJpmNFWUhRVJKCgkbpCyU0ESSlK2GKU2JjZ2ssJmJvDZKCAtvyV9nemiiuc+dk+fOOftzfp/nufec//8eyRwRsRY4DywBHgPngLPqz8wlx6eZOzkiRoClf82/CmxRI3fdLFBEzAPeTRK6Vb3cNKgLeD5J6Ki6rGnQAuB1RegK9VEOKveRzQU+VARuUy81CVoMPK0IPKnubxLUD1yvCDyj7m4SdCVt74rAw+qxRkARsQh4AsysCNyoXmsKlA6/zW3C5qtvOg6KiF5guE3QiLo8BzOl0hERs4CHQHebsFPq3iZAp4E6O2eNerejoIjoAW7XLMZ3gKlU/B/AGDCoDhkRtyp+zZ5WzXoApMOw0+NAAlW1CquBDcC+Tkta6z+rA9pZY5v/L+/30kD3SwJ9BHpLAY0CPepYKaD0Dp5QD5YE+grMKQmUjp/ZJYGG1b4SQF+AIWCX+rYEUPo66VNfjbcfNUpHEyf1BXVHSaCb6vqSQIfU46WAbgCb1M8lgI6qRya2CtP9Ur8HFqrffqOmG5QcXerLUkD3gFUTL7jq/EPb23w253aLL4B1amo9/ow6oE/ARWAlMCM3vTUvXeEkwCAwoP5zpfMLzjPicGiSuqUAAAAASUVORK5CYII="
            alt="vote"
          />
          <div class="downvote-count">{{ downvote }}%</div>
        </div>
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import { Component, Prop, Vue } from "vue-property-decorator";

@Component
export default class Box extends Vue {
  @Prop() public title!: string;
  @Prop() public text!: string;
  @Prop() public upvote!: string;
  @Prop() public downvote!: string;
  @Prop() public category!:string;
  @Prop() public image!: string;
  public voting = true;
  public selected=1;

  setActive(value:number) {
    this.selected = value;
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.content {
  height: 500px;
  padding: 30px;
  padding-top: 46%;
  background: url("../assets/malala.png");
  background-size: cover;
  background-position: right;
  overflow: hidden;
  .thanks{
      margin:23px 0px;
  }

  .voting-buttons {
    display: flex;
    margin: 21px 0px;
    div {
      display: flex;
    }
    .vote-link {
      height: 40px;
      padding: 6px 19px;
      border: thin solid white;
      display: initial;
      cursor: pointer;
      display: inline-block;
      border: thin solid white;
    }.active {
    border: 2px solid white;
}

    .up {
      background: #28bfb8;
      height: 40px;
      width: 40px;
      margin-right: 10px;
      cursor: pointer;
      img {
        width: 24px;
        height: 24px;
        margin: 7px;
      }
    }
    .down {
      background: #ffad1d;
      height: 40px;
      width: 40px;
      margin-right: 10px;
      cursor: pointer;
      img {
        width: 24px;
        height: 24px;
        margin: 7px;
        rotate: 180deg;
      }
    }
  }

  span {
    font-size: 12px;
    font-weight: bold;
  }
  h3 {
    font-weight: bold;
  }
  p.vote-text {
    margin-bottom: 0px;
  }
}
.rating {
  margin-top: 36px;
  height: 42px;
  margin-left: -30px;
  margin-right: -30px;
  display: flex;
  font-size: 24px;
  img {
    width: 21px;
    vertical-align: top;
  }

  .upvote {
    padding: 10px;
    background: #2a9994c2;

    img {
      float: left;
    }
    .span {
      float: left;
    }
    .upvote-count {
      float: left;
      margin-top: -5px;
      padding: 0 10px;
    }
  }
  .downvote {
    padding: 10px;
    background: #cf952fab;
    img {
      float: right;
      rotate: 180deg;
    }
    .span {
      float: right;
    }
    .downvote-count {
      float: right;
      margin-top: -5px;
      padding: 0 10px;
    }
  }
}
a.vote-link {
  border: thin solid white;
  padding: 10px;
  color: white;
  text-decoration: none;
}
.voting-box {
  color: white;
}
</style>
