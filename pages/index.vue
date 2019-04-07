<template>
  <h1 class="title-area">Immediately regret falling into bathtub</h1>
</template>

<script>
export default {
  layout: 'default'
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

  .title-area 
    font: bold 72px/80px 'Open Sans', Tahoma, serif
    font-style: normal
    text-align: center
    letter-spacing: 1.7px
    color: #FFFFFF
    display: block
    width: 750px
    height: 170px
    margin: 0
    background: linear-gradient(to right, #FFF 0%, #FFF 49.99%, #34495E 50%, #34495E 100%)
    -webkit-background-clip: text
    -webkit-text-fill-color: transparent
    +tablet
      margin: 0 auto
      -webkit-text-fill-color: unset
      width: 90%
      font-size: 45px
      line-height: 50px
    +mobile
      font-size: 36px
      line-height: 40px
</style>
