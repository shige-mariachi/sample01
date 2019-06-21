<template>
  <section>
    <nuxt-link to="/about">ABOUT</nuxt-link>
    <sample :title="indexTitle">
      <div class="come">
        slot example
      </div>
    </sample>
  </section>
</template>

<script>
import sample from '~/components/sample.vue'

export default {
  components: {
    sample
  },
  data() {
    return {
      indexTitle: 'シゲマリアッチのサイトだよ〜'
    }
  }
}
</script>

<style>
</style>
