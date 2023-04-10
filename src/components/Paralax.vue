
<script>
    import { ref, onMounted, onUnmounted } from 'vue'
    export default {
    setup() {
        const foreground = ref(null)
        const background = ref(null)
        const first = ref(null)
        const second = ref(null)
        return {
        foreground,
        background,
        first,
        second,
        }
    },
    }
    onMounted(() => {
        document.addEventListener('scroll', handleScroll)
    })
    onUnmounted(() => {
        document.removeEventListener('scroll', handleScroll)
    })

    const handleScroll = (evt) => {
  const scrollY = window.scrollY
  // decreases as user scrolls
  first.value.style.opacity =
    (100 - (scrollY + window.innerHeight - first.value.offsetHeight)) / 100
  // increases as user scrolls
  second.value.style.opacity =
    (scrollY + window.innerHeight - second.value.offsetTop) / 100
  const maxBackgroundSize = 120
  const backgroundSize = scrollY / (maxBackgroundSize - 100) // increases as user scrolls
  // zoom the background at a slower rate
  background.value.style.transform =
    'scale(' + (100 + backgroundSize * 0.4) / 100 + ')'
  foreground.value.style.transform =
    'scale(' + (100 + backgroundSize) / 100 + ')'
}
</script>

<template>
    <div class="root">
        <div class="background" ref="background"/>
        <div class="foreground" ref="foreground"/>
        <div class="section section-1" ref="first">
        <div>
            <h1>Parallax Made Easy.</h1>
        </div>
        </div>
        <div class="section section-2" ref="second">
        <div>
            <h2>Here's more info</h2>
            <p>Lorem ipsum dolor, sit amet consectetur adipisicing elit...</p>
        </div>
        </div>
    </div>
</template>

<style scoped>
    div.background,
    div.foreground {
        /* Fill background */
        min-height: 100%;
        min-width: 1024px;
        /* Scale proportionately */
        width: 100%;
        height: auto;
    }
    div.background {
        /* Positioning */
        position: fixed;
        top: 0;
        left: 0;
    }

    .section {
        min-height: 100vh;
        position: relative;
    }

    .section > div {
  position: fixed;
  color: white;
  /* centers this div */
  left: 50%;
  top: 50%;
  transform: translate(-50%, -50%);
}
.section-1 {
margin-bottom: 500px; /* determines the gap between our two sections */
font-size: 4em;
}
.section-2 {
  opacity: 0; /* defaults to 0 because it's not visible */
}
.section-2 div {
  background-color: rgba(255, 255, 255, 0.7);
  color: black;
  text-align: center;
  padding: 50px;
  max-width: 300px;
}
.section-2 h2 {
  font-size: 2em;
  margin-bottom: 40px;
}
.section-2 p {
  line-height: 150%;
}
</style>