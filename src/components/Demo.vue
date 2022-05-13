
<template>
    <div>
        <button @click="show = !show">
            Toggle
        </button>

        <transition
    @beforeEnter="beforeEnter"
    @enter="enter"
    @leave="leave"
    :css="false"
  >
    <Try v-if="show"/>
  </transition>

  <br>
  <br>
  <br>
  <br>
  <button @click="show = !show">Toggle</button>
    </div>
</template>

<script>
import gsap from 'gsap'
import Try from '@/components/Try'

export default {
    components: {
        Try
    },
    data() {
    return {
      show: false
    }
  },
  methods: {
    beforeEnter(el) {
        gsap.from(el, {
            opacity: 0,
        })
    },
    enter(el, done) {
      gsap.from(el, {
        delay: 0,
        y: -10,
        onComplete: done
      })
    },
    leave(el, done) {
      gsap.to(el, {
        delay: 1,
        opacity: 0,
      })
      gsap.to(el, {
        delay: 0.1,
        y: -20,
        onComplete: done
      })
    }
  }
    
}
</script>