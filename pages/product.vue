<template>
  <main class="product-container">
    <div class="product-left-side">
      <h1 class="product-title">Study case</h1>
      <p class="product-text">Run in circles show belly, lick paws then retire to the warmest spot on the couch to claw at the fabric.</p>
      <hooper :centerMode="true">
        <slide>
          <img class="product-image" src="@/static/chris-barbalis-249277.png" alt="wall-paint">
        </slide>
      </hooper>
    </div>
  </main>
</template>

<script>
import { Hooper, Slide } from 'hooper';
import 'hooper/dist/hooper.css';
export default {
    name: "product",
    components: {
      Hooper,
      Slide
    },
    props: {

    },
  data() { //local variables
      return {

      }
  },
  mounted() {

  },
  computed: {

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

  .product-container
    width: 100%
    height: 100%
    display: flex
    flex-direction: row
    justify-content: space-between

  .product-left-side
    position: relative
    width: 100%
    padding: 150px 0 0 14.375%
    +large-desktop
      padding: 50px 14.375% 50px 14.375%
    +small-desktop
      display: block

  .product-title
    z-index: 999
    position: relative
    font-family: "Open Sans", Tahoma, serif
    font-style: normal
    font-weight: bold
    line-height: 87px
    font-size: 64px
    letter-spacing: 2.88px
    color: #FFFFFF
    margin: 0 0 50px
    float: left
    +large-desktop
      width: 50%
      position: static
    +tablet
      float: none
      width: 100%
      text-align: center
      margin: 0

  .product-text
    z-index: 999
    position: relative
    font-family: "Open Sans", Tahoma, serif
    font-style: normal
    font-weight: 300
    line-height: 23px
    font-size: 16px
    letter-spacing: 0.72px
    color: #ECF0F1
    width: 201px
    float: right
    +large-desktop
      color: #34495E
      width: 40%
      font-size: 20px
      line-height: 29px
      position: static
    +tablet
      color: #ECF0F1
      float: none
      width: 100%
      text-align: center

  .hooper
    outline: none
    position: absolute
    top: 0
    left: 0
    height: 100%
    +large-desktop
      position: static
      height: auto
      margin: 0 auto
  .product-image
    position: absolute
    top: 13%
    left: 29.5%
    height: 515px
    background: #D8D8D8
    box-shadow: 2px 2px 7px rgba(0, 0, 0, 0.246801)
    +large-desktop
      position: static
      margin: 0 auto
    +small-desktop
      width: 100%
      height: auto

</style>
