<template>
  <transition
    mode="out-in"
    enter-active-class="animate__animated animate__fadeIn"
    leave-active-class="animate__animated animate__fadeOut"
  >
    <div class="share-container">
      <div class="share-icons">
        <p class="share-text">Share</p>
        <img :src="facebook" alt="Facebook Icon" class="facebook" />
        <img :src="twitter" alt="Twitter Icon" class="twitter" />
        <img :src="pinterest" alt="Pinterest Icon" class="pinterest" />
      </div>
      <div class="share-icon" @click="toggleShareOff">
        <img :src="shareWhite" alt="Share Icon" class="icon-white" />
      </div>
      <div class="pointer"></div>
    </div>
  </transition>
</template>
    
    <script>
import shareWhite from "./../../public/icon-share-white.svg";
import facebook from "./../../public/icon-facebook.svg";
import twitter from "./../../public/icon-twitter.svg";
import pinterest from "./../../public/icon-pinterest.svg";

export default {
  data() {
    return {
      facebook: facebook,
      twitter: twitter,
      pinterest: pinterest,
      shareWhite: shareWhite,
    };
  },
  methods: {
    toggleShareOff() {
      this.$emit("close");
    },
  },
};
</script>
    
    <style scoped>
.share-container {
  display: flex;
  justify-content: space-between;
  align-items: center;
  background-color: var(--very-dark-gray-blue);
  padding: 1.125rem 2rem;
  border-bottom-left-radius: 0.625rem;
  border-bottom-right-radius: 0.625rem;
}

.share-icons {
  width: 100%;
  display: flex;
  justify-content: space-between;
}

.share-text {
  line-height: 1.25rem;
  letter-spacing: 5px;
  color: var(--gray-blue);
  text-transform: uppercase;
}

.share-icons img {
  width: 1.25rem;
  height: 1.25rem;
}

.share-icons img:hover {
  cursor: pointer;
  animation: jello-horizontal 0.9s both;
}

.share-icon {
  display: flex;
  justify-content: center;
  align-items: center;
  border-radius: 50%;
  background-color: var(--desaturated-dark-blue);
  padding: 0.625rem;
  margin-left: 56px;
}

.share-icon:hover {
  cursor: pointer;
}

.icon-white {
  width: 15px;
  height: 15px;
}

.animate__animated.animate__fadeIn {
  --animate-duration: 0.5s;
}

.animate__animated.animate__fadeOut {
  --animate-duration: 0.5s;
}

@keyframes jello-horizontal {
  0% {
    transform: scale3d(1, 1, 1);
  }
  30% {
    transform: scale3d(1.25, 0.75, 1);
  }
  40% {
    transform: scale3d(0.75, 1.25, 1);
  }
  50% {
    transform: scale3d(1.15, 0.85, 1);
  }
  65% {
    transform: scale3d(0.95, 1.05, 1);
  }
  75% {
    transform: scale3d(1.05, 0.95, 1);
  }
  100% {
    transform: scale3d(1, 1, 1);
  }
}

@media screen and (min-width: 600px) {
  .share-icon {
    display: none;
  }

  .pointer {
    width: 1.25rem;
    height: 1.25rem;
    background-color: var(--very-dark-gray-blue);
    margin: 0 auto;
    transform: rotate(45deg);
    border-radius: 0 0 1px 0;
    margin-top: 3.125rem;
    position: relative;
    left: calc(0.5vw - 4px);
  }
}

@media screen and (min-width: 660px) {
  .pointer {
    left: calc(0.5vw - 8px);
  }
}

@media screen and (min-width: 760px) {
  .pointer {
    left: calc(0.5vw - 2rem);
  }
}

@media screen and (min-width: 810px) {
  .pointer {
    left: calc(0.5vw - 55px);
  }
}

@media screen and (min-width: 920px) {
  .pointer {
    left: calc(0.5vw - 82px);
  }
}
</style>