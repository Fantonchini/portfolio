<template>
  <div class="header">
    <div class="header-left">
      <nuxt-link to="/" class="stamp" :class="{'stamp-dark': isReversed}">Oregano</nuxt-link>
    </div>
    <div class="header-right padding-right-side">
      <h2 class="page-title" :class="{'page-title-dark': !isReversed, 'page-title-contacts': onTop}">{{ title }}</h2>
    </div>
  </div>
</template>

<script>
export default {
    name: "MyHeader",
    props: {

    },
  data() { //local variables
      return {

      }
  },
  mounted() {

  },
  computed: {
    isReversed() {
      return !!(this.$route.name === 'about' || this.$route.name === 'contacts')
    },
    onTop() {
      return !!(this.$route.name === 'contacts')
    },
    title() {
      switch (this.$route.name) {
        case 'index':
          return "let's get started"
          break
        case 'about':
          return 'who we are'
          break
        case 'product':
          return 'what we do'
          break
        case 'contacts':
          return 'get in touch'
          break
      }
    }
  },
  methods: {

  }
}
</script>

<style lang="sass" scoped>
  $large-desktop: 1600px
  $small-desktop: 1200px
  $large-tablet: 960px
  $tablet: 768px
  $mobile: 352px

  =large-desktop
    @media screen and (max-width: $large-desktop)
      @content
  =small-desktop
    @media screen and (max-width: $small-desktop)
      @content
  =large-tablet
    @media screen and (max-width: $large-tablet)
      @content
  =tablet
    @media screen and (max-width: $tablet)
      @content
  =mobile
    @media screen and (max-width: $mobile)
      @content

  @font-face
    font-family: Matura
    src: url('../static/MATURASC.TTF')

  .header
    width: 100%
    display: flex
    flex-direction: row
    position: relative
    z-index: 1010

  .header-left
    padding: 27px 0 0 14.375%
    width: 50%
    +tablet
      padding: 27px 0 0 0
      text-align: center

  .stamp
    text-decoration: none
    font-family: Matura, Tahoma, sans-serif
    font-size: 36px
    color: #ECF0F1
  .stamp-dark
    color: #34495E
  .header-right
    width: 50%
    padding-top: 33px
  .padding-right-side
    padding-left: 13.3125%
    +tablet
      padding-left: 0

  .page-title
    display: block
    font: 800 12px/15px 'Merriweather Sans', Tahoma, serif
    letter-spacing: 0.7px
    text-transform: uppercase
    text-align: center
    color: #ECF0F1
    text-decoration: none
    width: 100%
    margin-bottom: 0
    +tablet
      .about &
        color: #34495E

  .page-title-dark
    color: #34495E
    +tablet
      .index &
        color: #ECF0F1
      .product &
        color: #ECF0F1

  .page-title-contacts
    position: relative
    z-index: 999
    color: #34495E

</style>
