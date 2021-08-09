<template>
  <div class="escCont">

      <span class="text-2xl escText">
        hi. i like to
        <Transition mode="out-in" name="fade-in">
          <span :key="like">
            {{ like }}
          </span>
        </Transition>
        :)
      </span>
  </div>
</template>

<script>
export default {
  name: "EatSleepCode",
  data() {
    return {
      like: "code",
      likes: ["code","play soccer", "run", "write", "teach"],
      likePos: 1,
    }
  },
  methods: {
    changeLike(){
      if(this.likePos == this.likes.length){
        this.likePos = 0;
      }
      this.like = this.likes[this.likePos];
      this.likePos++;
      setTimeout(() => this.changeLike(),5000);
    }
  },
  mounted() {
    this.$nextTick(function (){
      setTimeout(() => this.changeLike(),6500);
    });
  }
}
</script>

<style>
.escCont {
  height: calc(100vh - 70px);
  width: 100%;
}

.escText {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  border-right: 2px solid rgba(255,255,255,.75);
  text-align: center;
  overflow: hidden;
  white-space: nowrap;
  animation: typewriter 1.5s steps(21) 1s 1 normal both,
  blinkTextCursor 500ms steps(21) infinite normal;
}

@keyframes typewriter{
  0%{width: 0;}
  99%{width: 8.3em;}
  100%{width: auto;}
}
@keyframes blinkTextCursor{
  from{border-right-color: rgba(255,255,255,.75);}
  to{border-right-color: transparent;}
}

.fade-in-enter-active {
  animation: fadeInActive 2s;
}

@keyframes fadeInActive {
  from {opacity: 0;}
  to {opacity: 1;}
}

.fade-in-leave-active {
  animation: fadeOutActive 1s;
}

@keyframes fadeOutActive {
  from {opacity: 1;}
  to {opacity: 0;}
}

.fade-in-enter,
.fade-in-leave-to {
  opacity: 0;
}
</style>