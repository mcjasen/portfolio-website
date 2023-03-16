<template>
  <div id="app">
      <TheNavigation />
      <TheSliders />
      <router-view />
      <TheFooter />
  </div>
</template>

<!-- ----- ----- ----- ----- ----- ----- ----- VUE SCRIPT CONFIGURATION ----- ----- ----- ----- ----- ----- ----- -->

<script>
import TheNavigation from './components/TheNavigation.vue';
import TheSliders from './components/TheSliders.vue';
import TheFooter from './components/TheFooter.vue';

export default {
  beforeCreate() {
      const appHeight = () => {
          const root = document.documentElement;
          root.style.setProperty('--app-height', `${window.innerHeight}px`);
      }
      window.addEventListener('resize', appHeight);
      appHeight();
  },

  name: 'App',
  components: {
      TheNavigation: TheNavigation,
      TheSliders: TheSliders,
      TheFooter: TheFooter,
  },
}
</script>

<!-- ----- ----- ----- ----- ----- ----- ----- STYLESHEET CONFIGURATION ----- ----- ----- ----- ----- ----- ----- -->

<style lang="scss">
@font-face {
  font-family: 'Averta Bold';
  src: url('./assets/fonts/Averta/Averta-Bold.ttf') format('truetype');
}

@font-face {
  font-family: 'Averta Light';
  src: url('./assets/fonts/Averta/Averta-Light.ttf') format('truetype');
}

@font-face {
  font-family: 'SFMono Regular';
  src: url('./assets/fonts/SFMono/SFMono-Regular.ttf') format('truetype');
}

:root {
  --app-height: 100%;

  --font-mark: 'Averta Bold';
  --font-text: 'Averta Light';
  --font-code: 'SFMono Regular';

  --size-sm: 14px;
  --size-md: 16px;
  --size-lg: 20px;
  --size-xl: 24px;

  --headline-sm: 30px;
  --headline-md: 40px;
  --headline-lg: 80px;

  --header-scroll-color: #0a242fd1;
  --background-shadow: #0A242F;
  --background-normal: #0A242F;
  --background-accent: #283446;
  --background-opposite: #F1F4FA;

  --timeline-color: #5A6978;
  --timeline-opposite-color: #B7BEC6;

  --font-color-normal: #FFFFFF;
  --font-color-accent: #BDBDBD;
  --font-color-accent2: #D6D6D6;

  --accent-color: #81FFD9;
  --accent-hover: #1D303B;

  --heading-line-color: #185977;
}

/*@media (prefers-color-scheme: dark) {
  :root {
      --header-scroll-color: rgba(21, 30, 44, 0.85);
      --background-shadow: #131B28;
      --background-normal: #0A242F;
      //--background-normal: black;
      --background-accent: #283446;
      --background-opposite: #F1F4FA;

      --timeline-color: #616A77;
      --timeline-opposite-color: #B7BEC6;

      --font-color-normal: #C6C8CD;
      --font-color-accent: #F7F7F7;

      --accent-color: #81FFD9;
      --accent-hover: #1D303B;
  }
}*/

* {
  // TODO: maybe add "cursor: pointer;"
  box-sizing: border-box;
  padding: 0;
  margin: 0;
}

body {
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;

  background-color: var(--background-normal);
  color: var(--font-color-normal);
  font-family: var(--font-text);
}

a {
  text-decoration: none;
}

header, section {
  min-height: var(--app-height);
  width: 1000px;
  margin: auto;

  display: flex;
  flex-direction: column;
  justify-content: center;
}

@media (max-width: 1260px) {
  header, section {
      width: auto;
      margin: 0 120px;
  }
}

@media (max-width: 1080px) {
  header, section {
      width: auto;
      margin: 0 90px;
  }
}

@media (max-width: 956px) {
  header, section {
      width: auto;
      margin: 0 80px;
  }
}

//768 alles abschalten
@media (max-width: 768px) {
  header, section {
      width: auto;
      margin: 0 40px;
  }
}

@media (max-width: 546px) {
  header, section {
      width: auto;
      margin: 0 20px;
  }
}

.retro-btn {
  padding: 18px 30px;
  font-family: var(--font-code);
  font-size: var(--font-lg);
  color: var(--accent-color);
  border: 1px solid var(--accent-color);
  border-radius: 6px;
}

.retro-btn:hover {
  background-color: var(--accent-hover);
}

.section-header{
  h1 {
      font-family: var(--font-code);
      color: var(--font-color-accent);
      margin-bottom: 40px;
      font-size: 35px;
      display: flex;
      align-items: center;
      white-space: nowrap;

      .number {
          color: var(--accent-color);
          font-size: 30px;
          padding-right: 5px;
      }

      .line{
          content : "";
          display:block;
          height: 1px;
          width: 100%;
          margin-left: 20px;
          background-color: var(--heading-line-color);
      }
  }
}

.list{
  ul{
      list-style: none;
  }

  li{
      padding-left: 17.5px;
      text-indent: -17.5px;
  }

  li:before{
      content: "‣";
      color: var(--accent-color);
      padding-right: 10px;
  }
}
</style>