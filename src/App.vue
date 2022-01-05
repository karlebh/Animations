
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
        Lorem, ipsum dolor sit amet consectetur adipisicing elit. Commodi tempore officiis aperiam similique eveniet aut tenetur vel ipsa sit, culpa, debitis praesentium dolore cumque eius ratione totam modi in officia nam architecto explicabo perferendis quod nisi vitae? Laborum, ab. Rem sint modi rerum numquam, qui ipsam, similique eum libero error id accusantium hic ipsum dignissimos recusandae consequuntur ullam cum. Adipisci esse vitae molestias tenetur. Necessitatibus, laudantium! Itaque, numquam neque repellat quas. Excepturi, voluptatibus, aut earum ullam itaque, dolor numquam, veritatis quaerat vero ipsa aliquam nemo eos! Aspernatur id modi nostrum omnis, voluptates eos quibusdam possimus consequuntur facilis quas atque mollitia excepturi ullam odit laboriosam esse adipisci repellat, aliquam tempora. Quo vitae eum quae numquam error sequi corporis asperiores sint quasi omnis ex porro nobis, illo beatae sunt sit consequatur voluptate enim iste soluta. Distinctio quam, sit quas voluptatem recusandae ullam magni deserunt incidunt eligendi expedita qui cumque laborum, libero amet nobis temporibus illo. Tempora quidem laborum aspernatur architecto ab cupiditate quos repellendus quibusdam perferendis voluptatum animi accusamus vero alias odit, reiciendis sequi vitae id fugiat dignissimos voluptates? Deserunt nisi similique optio nulla assumenda reiciendis quos at voluptate voluptates, perspiciatis. Labore voluptatibus numquam dolores possimus delectus? Ducimus animi rerum velit vel debitis quo error, odio nisi nobis iure sapiente iusto saepe ullam mollitia ea distinctio sit reiciendis ut expedita quaerat vitae incidunt porro. Nulla quam, ducimus odio quas maiores sint officiis animi autem nemo, vel? Placeat ex assumenda, expedita officia consequatur laborum harum? Sit quis voluptas consequatur quas alias voluptates asperiores eveniet quia iste iure, officia culpa, laboriosam laudantium voluptatum commodi nobis dolorum veniam quo nulla, libero totam? Laboriosam voluptas pariatur odio nisi, inventore debitis dolorum reprehenderit labore ea nam necessitatibus molestias rem omnis illo quo sunt corporis repellendus sequi sit! Dicta nisi voluptatem ipsum aliquam ad consequuntur similique mollitia asperiores eaque dolore pariatur itaque cupiditate magni totam officiis, fugit. Deleniti nulla doloribus nisi modi officia cupiditate soluta eveniet? Facilis nemo minus, vero itaque ipsum nihil quasi consequuntur fugiat rem consequatur aut sapiente molestiae in deserunt illo! Accusamus neque rem earum incidunt dolorum sed harum consequatur accusantium qui aperiam voluptas libero, eligendi laborum quo nulla asperiores at laudantium corporis enim nam quia, iure quos minima iusto facilis. Dolorum accusantium, voluptatem vitae voluptatibus dolore rem nostrum dignissimos dolor. Eos iste molestiae cum hic accusamus et temporibus ad recusandae quidem officia, iure est impedit quaerat dolore quo porro non maiores corporis vel itaque minima laudantium assumenda, illum harum animi? Deleniti dolor autem et possimus quis, eos? Vitae fugiat deserunt ipsum similique laudantium adipisci impedit enim reiciendis maiores commodi numquam, consequuntur dicta expedita, quisquam sed ea neque quae excepturi fugit possimus. Molestias quae id expedita, consectetur atque labore. Quis ullam minima modi, quidem alias, tenetur harum nisi libero quae odio nemo quo ipsam. Sit eius inventore repudiandae, saepe expedita accusantium quasi ex excepturi corporis asperiores repellat blanditiis eligendi commodi, iste autem mollitia eveniet deserunt similique maxime, quaerat dolorum vero? Ipsa est repudiandae illo. Perspiciatis at reiciendis corrupti, debitis maxime consectetur fugit eum sunt rem!
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

export default {
  name: 'App',
  components: {
    NewAnimation,
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

