<script setup>
import { useDark, useToggle } from "@vueuse/core";

const isDark = useDark();
const toggleDark = useToggle(isDark);
</script>

<template>

  <nav class="nav" flex="~" justify-between m-au>
    <div class="title" >
      <div font="sans 700">
        PickMyColor
      </div>

      <div class="bar" m-au w-cen />
    </div>
    <button class="githubIcon" w-cen w-right>
      <a href="https://github.com/2803713783/pickMyColor" target="_blank">
        <span class="i-carbon:logo-github">git</span>
        <span>star</span>
      </a>
    </button>
    <button class="icon-btn !outline-none" @click="toggleDark()">
      <div v-if="isDark" i-carbon-moon />
      <div v-else i-carbon-sun />
      <span class="ml-2">{{ isDark ? "Dark" : "Light" }}</span>
    </button>
  </nav>
</template>

<style scoped>
/* 超小屏幕（手机，小于 768px） */
@media (max-width: 768px) {

  .nav {
    margin: auto;
    padding: 0;
    flex-direction: row;
    
  }
  .title {
    margin-left: 5rem;
    margin-right: 5rem;
    font-size: 13rem;
    justify-content: flex-start
  }

  .bar {
    height: 7px;
    width: 70rem;
    background: linear-gradient(-45deg, #ee7752, #e73c7e, #23a6d5, #6f8681, #D9AFD9, #97D9E1);
    background-size: 700% 700%;
    animation: barcolor 5s ease infinite;
    border-radius: 16px;

  }


.githubIcon span {
  padding: 0.5vh;
}

.bar {
  height: 7px;
  width: 50px;
  background: linear-gradient(
    -45deg,
    #ee7752,
    #e73c7e,
    #23a6d5,
    #6f8681,
    #d9afd9,
    #97d9e1
  );
  background-size: 700% 700%;
  animation: barcolor 5s ease infinite;
  border-radius: 16px;

  @keyframes barcolor {
    0% {
      background-position: 0% 50%;
    }

    50% {
      background-position: 100% 50%;
    }

    100% {
      background-position: 0% 50%;
    }
  }

}

/* 大屏幕（大桌面显示器） */
@media (min-width: 769px) {
  .nav {
    margin: auto;
    width: 60vw;
  }

  .bar {
    height: 7px;
    width: 200px;
    background: linear-gradient(-45deg, #ee7752, #e73c7e, #23a6d5, #6f8681, #D9AFD9, #97D9E1);
    background-size: 700% 700%;
    animation: barcolor 5s ease infinite;
    border-radius: 16px;

  }
  .title{
    font-size: 15rem;
  }

  @keyframes barcolor {
    0% {
      background-position: 0% 50%;
    }

    50% {
      background-position: 100% 50%;
    }

    100% {
      background-position: 0% 50%;
    }
  }
}
</style>
