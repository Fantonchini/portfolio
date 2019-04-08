<template>
  <main class="about-container">
    <div class="background-ring"></div>
    <div class="about-container-left">
      <img class="plate-quotes" src="@/static/Quotes.svg" alt="quotes">
        <p class="about-plate-text">My left donut is missing, as is my right destroy the blinds.
          Cat snacks cough hairball on conveniently placed pants cough furball for scratch at
          fleas scratch strangers and dream about hunting birds. <span class="ring"></span></p>
    </div>
    <div class="about-container-right">
      <div class="about-right-text-area">
        <p class="about-right-text">Run outside as soon as door open. Eat all the power cords refuse to drink water except out of someone's glass purr so eat all the power cords but purr, and sit on human meow. Dream about hunting birds. Kitty kitty kitty poochy, yet intrigued by the shower.</p>
        <p class="about-right-text">Hiss and stare at nothing then run suddenly away. Stare out the window destroy couch, and meow meow loudly just to annoy owners for spit up on light gray carpet instead of adjacent linoleum but need to chase tail. Stare out the window nap all day claw drapes ask for petting and make a weird face.</p>
        <p class="about-right-text">Knock dish off table rub face on owner need to chase tail, yet freak human out make funny noise mow mow mow mow mow mow success now attack human, attack feet. Present belly, scratch hand when stroked pounce on unsuspecting person yet chase mice. Hide head under blanket so no one can see. Slap owner's face until human fills food dish.</p>
      </div>
    </div>
  </main>
</template>

<script>
    export default {
        name: "about",
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

  .about-container
    position: relative
    width: 100%
    display: flex
    flex-direction: row
    +tablet
      flex-direction: column
      justify-content: center
      align-items: center
      flex-grow: 1
      padding-top: 20px

  .about-container-left
    position: relative
    display: flex
    flex-direction: column
    justify-content: flex-start
    align-items: flex-start
    width: 50%
    padding: 195px 0 0 14.375%
    +large-desktop
      display: flex
      flex-direction: column
      justify-content: center
      padding: 0 5% 0 7%
    +tablet
      width: 80%
      padding: 0
      display: flex
      flex-direction: column
      justify-content: center
      align-items: center

  .about-container-right
    position: relative
    padding-left: 6.8125%
    padding-top: 106px
    width: 50%
    height: 100%
    +large-desktop
      padding: 0 7% 0 5%
      display: flex
      flex-direction: column
      justify-content: center
    +tablet
      width: 80%
      padding: 20px
      display: flex
      flex-direction: row
      justify-content: center
      align-items: center

  .about-plate-text
    z-index: 999
    position: relative
    margin: 0
    font-family: "Merriweather Sans", Tahoma, serif
    font-style: normal
    font-weight: bold
    line-height: 25px
    font-size: 18px
    letter-spacing: 1.37143px
    color: #34495E
    text-shadow: 0 4px 4px rgba(0, 0, 0, 0.25)
    width: 480px
    +large-desktop
      font-size: 14px
      width: 90%
    +large-tablet
      font-size: 12px
      width: 85%

  .ring
    z-index: -1
    top: 0
    left: 0
    right: 0
    bottom: 0
    position: absolute
    margin: auto
    display: block
    width: 87px
    height: 87px
    border-radius: 50%
    box-shadow: 0 0 0 3px rgba(52, 73, 94, .03), 0 0 0 48px #ECF0F1, 0 0 0 52px rgba(52, 73, 94, .03), 0 0 0 92px #ECF0F1, 0 0 0 97px rgba(52, 73, 94, .03), 0 0 0 142px #ECF0F1, 0 0 0 148px rgba(52, 73, 94, .03)
    +large-desktop
      transform: scale(0.9)
    +tablet
      display: none

  .plate-quotes
    position: relative
    z-index: 1000
    margin-bottom: 35px
    +large-desktop
      margin-bottom: 20px
      max-width: 32px
      height: auto
    +large-tablet
      margin-bottom: 16px
      max-width: 26px
    +tablet
      margin: 0 16px 0 0

  .about-right-text-area
    z-index: 999
    width: 483px
    overflow-y: scroll
    +large-desktop
      width: 100%
      height: 98%
      display: block
    +large-tablet
      width: 100%
    +tablet
      width: 100%

  .about-right-text
    z-index: 999
    font: 400 15px/21px 'Merriweather Sans', Tahoma, serif
    letter-spacing: 1.28571px
    color: #ECF0F1
    text-align: left
    margin: 0 0 18px
    +large-desktop
      font-size: 17px
      line-height: 20px
    +small-desktop
      font-size: 14px
      line-height: 17px
    +large-tablet
      font-size: 12px
      line-height: 15px
    +tablet
      color: #34495E

  .background-ring
    position: absolute
    top: 0
    left: 0
    right: 0
    bottom: 0
    width: 197px
    height: 197px
    border-radius: 50%
    margin: 16% -92px auto auto
    box-shadow: 0 0 0 3px rgba(236, 240, 241, .03), 0 0 0 92px #34495E, 0 0 0 98px rgba(236, 240, 241, .03), 0 0 0 186px #34495E, 0 0 0 194px rgba(236, 240, 241, .03), 0 0 0 290px #34495E, 0 0 0 299px rgba(236, 240, 241, .03)
    +large-desktop
      display: none
    +tablet
      box-shadow: 0 0 0 3px rgba(52, 73, 94, .03), 0 0 0 48px #ECF0F1, 0 0 0 52px rgba(52, 73, 94, .03), 0 0 0 92px #ECF0F1, 0 0 0 97px rgba(52, 73, 94, .03), 0 0 0 142px #ECF0F1, 0 0 0 148px rgba(52, 73, 94, .03)
      display: block
      transform: scale(0.8)
      margin: auto auto
</style>
