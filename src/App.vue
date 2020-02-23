<template>
  <div id="app">
    <section class="bg-1 animation-fade">
      <h1>Intersection observer example</h1>
    </section>
    <section id='avocado-section'>
      <template v-if="avocadoVisible">
        <svg class="avocado" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 108.14 126"><path class="cls-1" d="M68.87,65.08c-2.75-9-4.35-6.7-8.69-18.48C52.31,25.26,56,13.22,46.6,6.25A21.13,21.13,0,0,0,36.4,2.49,21.14,21.14,0,0,0,26.19,6.25c-9.36,7-5.71,19-13.57,40.35C8.27,58.38,6.67,56,3.92,65.08c-2.43,8-8.69,27.89,2.66,44.13C12.7,118,24.36,126.26,36.4,126c12,.27,23.69-8,29.81-16.78C77.57,93,71.3,73.07,68.87,65.08Z"/><path class="cls-2" d="M50.43,57.4c-1.33-7-2.36-5.24-4.55-14.36-4-16.52-1.37-25.64-6.7-31.21a11.29,11.29,0,0,0-5.94-3.14,12.81,12.81,0,0,0-6.2,2.6c-4.85,3.93-3.79,9.86-6.39,23.49-1.09,5.65-2,10.95-4.46,17.32-3.62,9.38-6,9.53-8.42,16.55-1.22,3.54-5,14.54,0,25.19,3.32,7,11.59,16.24,21.29,15.3,10-1,15.34-12,18.29-18.08C47.35,91.06,54.2,77.26,50.43,57.4Z"/><path class="cls-3" d="M28.2,77.71c.57-3.49-.14-6.18-1.08-9.8s-1.85-7.07-4.41-7.83a5.84,5.84,0,0,0-4.07.68,9.55,9.55,0,0,0-3.51,3.43,23.48,23.48,0,0,0-2,3.7c-.65,1.33-1.45,3-2,4.42-.68,1.86-2.12,5.47-1.24,8.83,1.15,4.4,5.45,9,9.88,8.54C26.22,89,28.12,78.19,28.2,77.71Z"/><path class="cls-1" d="M104,63.85c-2.91-9.23-4.6-6.83-9.2-18.85C86.47,23.23,90.34,10.94,80.43,3.83A22.89,22.89,0,0,0,69.64,0a23,23,0,0,0-10.8,3.83c-9.9,7.11-6,19.4-14.36,41.17-4.59,12-6.29,9.62-9.2,18.85-2.56,8.15-9.19,28.45,2.82,45,6.47,8.93,18.8,17.39,31.54,17.12,12.73.27,25.06-8.19,31.54-17.12C113.19,92.3,106.56,72,104,63.85Z"/><path class="cls-4" d="M102.11,63.84c-2.75-9.05-4.35-6.7-8.69-18.48C85.55,24,89.21,12,79.84,5a21.36,21.36,0,0,0-10.2-3.76A16.26,16.26,0,0,0,68,1.45l-.24,0c-.49.09-1,.2-1.44.33l-.25.06q-.7.19-1.35.42l-.13,0A21.62,21.62,0,0,0,59.43,5c-9.36,7-5.7,19-13.57,40.36-4.35,11.78-6,9.43-8.7,18.48-2.43,8-8.69,27.88,2.66,44.12,5,7.22,13.84,14.1,23.51,16.16h0c.82.18,1.64.31,2.47.41.37,0,.75.09,1.13.12l.75.06c.65,0,1.3.05,2,0,12,.26,23.69-8,29.81-16.79C110.81,91.72,104.54,71.82,102.11,63.84Z"/><path class="cls-10" d="M85.93,61.55c-4.09-5.75-9.73-9.68-15.41-9.66-12.47,0-24.27,19-20.81,34.68,1.32,6,5.23,13.06,11,17,3.58,5.18,8.86,9.34,15.41,9.55,11.59.37,20.14-11.86,21.9-21.9C100.07,79.87,94.06,67.29,85.93,61.55Z"/><path class="cls-6" d="M91.69,84.75c2.69-15.33-9.17-32.89-21.17-32.86-12.47,0-24.27,19-20.81,34.68,1.92,8.66,9.29,19.74,20.08,20.08C81.38,107,89.93,94.79,91.69,84.75Z"/><path class="cls-7" d="M70.93,52.73c-12.48,0-24.28,19.05-20.81,34.68a30,30,0,0,0,2.82,7.49,17.91,17.91,0,0,0,11.78,5.28c11.59.37,20.14-11.86,21.9-21.9,1.19-6.78-.47-14-3.72-19.92C79.34,54.89,75.14,52.72,70.93,52.73Z"/><path class="cls-8" d="M49.71,86.57c.08.37.2.75.3,1.13a15.7,15.7,0,0,0,4.08.69c11.59.37,20.15-11.86,21.91-21.9a29.23,29.23,0,0,0-1.13-13.85,13.4,13.4,0,0,0-4.35-.75C58.05,51.91,46.25,70.94,49.71,86.57Z"/><path class="cls-9" d="M58.73,68.5l.12.46a6.48,6.48,0,0,0,1.66.28c4.68.15,8.14-4.8,8.85-8.86a11.72,11.72,0,0,0-.45-5.6,5.66,5.66,0,0,0-1.76-.3C62.1,54.49,57.33,62.18,58.73,68.5Z"/>
          <text
            x="50%"
            y="100%"
            text-anchor="middle"
            dominant-baseline="text-before-edge"
            font-weight="bold"
            class="animation-fade avocado-text"
          >Avocado</text>
        </svg>
      </template>
    </section>
  </div>
</template>

<script>
export default {
  name: 'App',
  data() {
    return {
      avocadoVisible: false,
    }
  },
  mounted() {
    const self = this,
          avocadoContainer = document.querySelector('#avocado-section')

    let observer = new IntersectionObserver((entries, observer) => {
      if (entries[0].intersectionRatio >= .6) self.avocadoVisible = true
      if (entries[0].intersectionRatio <= .1) self.avocadoVisible = false
    }, {threshold: [.1, .6]})

    observer.observe(avocadoContainer)
  }
}
</script>

<style lang="scss">
:root {
  font-size: 10px;
}
h1 {
  @media screen and (min-width: 900px) {
    font-size: 4.2rem;
  }
  font-size: 3.6rem;
}
body {
  margin: 0;
  & * {
    box-sizing: border-box;
  }
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
.avocado {
  width: 60%;
  max-height: 60%;
  overflow: visible;
}
@for $i from 1 through 9 {
  .cls-#{$i} {
    animation-duration: 1s;
    animation-delay: 0;
    animation-iteration-count: 1;
    animation-timing-function: cubic-bezier(0.075, 0.82, 0.165, 1);
    @if $i <= 5 {
      animation-name: testAnimation1;
    }
    @else {
      animation-name: testAnimation2;
    }
  }
}
.cls-10 {
  animation-name: testAnimation3;
  animation-delay: 0;
  animation-duration: 1s;
  animation-timing-function: cubic-bezier(0.165, 0.84, 0.44, 1);
  animation-iteration-count: 1;
  animation-fill-mode: forwards;
  opacity: 0;
  display: none;
}
@keyframes testAnimation1 {
  0% {
    transform: translate(-100%, 0);
    fill-opacity: 1;
  }
  100% {
    transform: translate(0, 0);
    fill-opacity: 1;
  }
}

@keyframes testAnimation2 {
  0% {
    transform: translate(100%, 0);
  }
  100% {
    fill-opacity: 1;
    opacity: 1;
  }
}

@keyframes testAnimation3 {
  0% {
    transform: translate(100%, 0);
  }
  75% {
    opacity: 0;
  }
  100% {
    opacity: 1;
  }
}

section {
  display: flex;
  align-items: center;
  justify-content: center;
  height: 100vh;
  width: 100vw;
  border: .5rem solid white;
  border-radius: .5rem;
}

.bg-1 {
  background-color: rgba(22,122,58, .2);
}

.animation-fade {
  opacity: 0;
  animation-name: animateOpacity;
  animation-duration: .8s;
  animation-delay: .3s;
  animation-fill-mode: forwards;
  animation-timing-function: cubic-bezier(0.175, 0.885, 0.32, 1.275);
}

.avocado-text {
  @media screen and (min-width: 900px) {
    font-size: 1.2rem;
  }
  font-size: 1.6rem;
}

@keyframes animateOpacity {
  100% {
    opacity: 1;
  }
}
</style>

<style>.cls-1{fill:#4c8930;}.cls-2{fill:#529535;}.cls-3{fill:#689f5f;}.cls-4{fill:#90b973;}.cls-5, .cls-10{fill:#7a9e63;}.cls-6{fill:#512b1d;}.cls-7{fill:#5d3223;}.cls-8{fill:#6a392a;}.cls-9{fill:#814535;}</style>