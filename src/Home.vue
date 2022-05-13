
<template>
  <div id="app">
    <header>
      <h1>Music</h1>

      <div class="nav">
        <a href="#">Piano</a>
        <a href="#">Guitar</a>
        <a href="#">Drums</a>
        <a href="#">Bass</a>
      </div>
    </header>

    <main>
      <aside>
        <div>
          <button>Menu 1</button>
          <button>Menu 2</button>
          <button>Menu 3</button>
          <button>Menu 4</button>
        </div>
      </aside>

      <section>
        <Demo/>
      </section>
    </main>

    <footer>
      <p>
        Music &copy; <span id="year"></span>
      </p>
    </footer>

    <NewAnimation/>
  </div>
</template>


<script>
import gsap from 'gsap'
import NewAnimation from '@/components/NewAnimation'
import Demo from '@/components/Demo'

export default {
  name: 'App',
  components: {
    NewAnimation,
    Demo,
  },

  mounted() {
    document.getElementById('year').innerHTML = new Date().getFullYear()

    gsap.from('header', {delay: 1.2, duration: 1, y: '-10rem'});
    gsap.from('aside', {delay: 1.4, duration: 1, opacity:0, x: '30rem', ease: 'back.out(1.7)'});
    gsap.from('section', {delay: 1.6, duration: 1, opacity:0, x: '30rem', ease: 'back.out(1.0)'});
  }
}
</script>

<style>
#app {
  font-family: Helvetica, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  margin: 0;
  padding: 0;
}

header {
  display: flex;
  justify-content: space-between;
  align-items: baseline;
  background: teal;
  color: #eee;
}

header h1 {
  margin-left: 2rem;
}

.nav {
  margin-right: 10rem;
}

.nav a {
  text-decoration: none;
  margin-right: 2rem;
  color: #eee;
}

aside {
  background: #ddd;
  min-width: 300px;
  height: 600px;
  display: flex;
  flex: 1;
}

aside div {
  display: flex;
  flex-direction: column;
  align-items: center;
  margin-left: 4rem;
  margin-top: 5rem;
}

aside > div button {
  width:  12rem;
  margin-top:  1rem;
  height: 3.3rem;
  cursor: pointer;
  background: teal;
  color: #fee;
  font-size: 1.3rem;
  border-radius: 7px 12px;
  border: 1px solid rgba(0, 0, 0, .4);
  transition: color .3s ease-in-out, background .3s ease-in-out;
}

aside > div button:hover {
  color: teal;
  background: #fee;
}

main {
  display: flex;
}

section {
  flex: 4;
  margin: 1rem;
  font-family: Verdana, sans-serif;
}

footer {
  height: 100px;
  display: flex;
  justify-content: center;
  align-items: center;
  background: #bbb;
  font-size: 1.5rem;
  font-weight: 500;
}

</style>

