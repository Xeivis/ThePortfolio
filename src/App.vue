<script setup>
  import { useDark, useFavicon } from "@vueuse/core"
  import HelloWorld from './components/HelloWorld.vue'
  import TheWelcome from './components/TheWelcome.vue'
  import lightThemeLogo from "./assets/logoBlack.svg"
  import darkThemeLogo from "./assets/logoWhite.svg"
  import lightThemeIco from "/icoMinBlack.ico"
  import darkThemeIco from "/icoMinWhite.ico"
  
  let image
  let ico = useFavicon()

  if (useDark().value) {
    image = darkThemeLogo
    ico.value = darkThemeIco
  } else {
    image = lightThemeLogo
    ico.value = lightThemeIco
  }

  useDark({
    onChanged(dark){
      if (dark) {
        image = darkThemeLogo
        ico.value = darkThemeIco
      } else {
        image = lightThemeLogo
        ico.value = lightThemeIco
      }
    }
  })

</script>

<template>
  <header>

    <img v-bind:src="image" alt="Xeivis logo" class="logo" width="125" height="125" />

    <div class="wrapper">
      <HelloWorld msg="Hello there!" />
    </div>
  </header>

  <main>
    <TheWelcome />
  </main>
</template>

<style scoped>
header {
  line-height: 1.5;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }
}
</style>
