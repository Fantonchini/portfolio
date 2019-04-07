<template>
  <section id="main-area" :class="pageNavigator">
    <div  class="container" :class="{'container-reverse': isReversed}">
      <my-header/>
        <nuxt />
      <my-footer/>
    </div>
  </section>
</template>

<script>
import MyHeader from '@/components/header'
import MyFooter from '@/components/footer'
export default {
  components: {
    MyHeader,
    MyFooter
  },
  name: "default",
  props: {

  },
  data() { //local variables
    return {
      index: false,
      about: false,
      product: false,
      contacts: false
    }
  },
  mounted() {
  },
  computed: {
    isReversed() {
      return !!(this.$route.name === 'about' || this.$route.name === 'contacts')
    },
    pageNavigator() {
      return {
        index: this.$route.name === 'index',
        about: this.$route.name === 'about',
        product: this.$route.name === 'product',
        contacts: this.$route.name === 'contacts',
      }
    }
  },
  methods: {

  }
}
</script>

<style lang="sass">
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

  html, body  
    padding: 0
    margin: 0
    box-sizing: border-box
    height: 100%
    min-height: 100%
  #__nuxt, #__layout
    height: 100%
  div 
    box-sizing: border-box
  #main-area
    height: 100%
    min-height: 100%
    background: #ffffff
    display: flex
    justify-content: center
    align-items: center
  .container 
    position: relative
    background: linear-gradient(to right, #34495E 0%, #34495E 50%, #ECF0F1 50.01%, #ECF0F1 100%)
    height: 820px
    width: 1600px
    min-width: 320px
    display: flex
    flex-direction: column
    justify-content: space-between
    align-items: center
    overflow: hidden

    +large-desktop
      height: 100%
      overflow-y: visible
    +tablet
      .index &
        background: #34495E
      .product &
        background: #34495E
      .about &
        background: #ECF0F1
      .contacts &
        background: #ECF0F1
  .container-reverse 
    background: linear-gradient(to right, #ECF0F1 0%, #ECF0F1 50%, #34495E 50.01%, #34495E 100%)
</style>
