<template>
  <div class="footer">
    <div class="footer-left">
      <nav class="menu">
        <ul class="menu-list" :class="{'menu-list-dark': isReversed}">
          <li class="menu-item">
            <nuxt-link to="/about" class="menu-link" :class="isAbout ? 'selected-dark' : ''">About</nuxt-link>
          </li>
          <li class="menu-item">
              <nuxt-link to="/product" class="menu-link" :class="isProduct ? 'selected' : ''">Products</nuxt-link>
          </li>
          <li class="menu-item">
            <nuxt-link to="/contacts" class="menu-link" :class="isContacts ? 'selected-dark' : ''">Contact</nuxt-link>
          </li>
        </ul>
      </nav>
    </div>
    <div class="footer-right padding-right-side">
      <ul class="social-list" :class="{'social-list-dark': !dark}">
        <li class="social-item">
          <a class="social-link" href="https://twitter.com/Fanton4ini" target="_blank">
            <i class="fab fa-twitter"></i>
          </a>
        </li>
        <li class="social-item">
          <a class="social-link" href="https://www.linkedin.com/in/vladimir-amatov-297606182" target="_blank">
            <i class="fab fa-linkedin-in"></i>
          </a>
        </li>
        <li class="social-item">
          <a class="social-link" href="https://www.facebook.com/vladimir.amatov" target="_blank">
            <i class="fab fa-facebook"></i>
          </a>
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
    export default {
        name: "MyFooter",
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
        dark() {
          return !!(this.$route.name === 'about')
        },
        isContacts() {
          return !!(this.$route.name === 'contacts')
        },
        isAbout() {
          return !!(this.$route.name === 'about')
        },
        isProduct() {
          return !!(this.$route.name === 'product')
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

  .footer
    width: 100%
    display: flex
    flex-direction: row
    +tablet
      flex-direction: column
      align-items: center

  .footer-left
    width: 50%
    display: flex
    flex-direction: column
    justify-content: flex-end
    align-items: center
    padding-bottom: 75px
    +tablet
      width: 100%
      padding-bottom: 27px

  .footer-right
    width: 50%
    display: flex
    flex-direction: column
    justify-content: flex-end
    align-items: center
    padding-bottom: 72px
    +tablet
      width: 100%
      padding-bottom: 27px

  .padding-right-side
    padding-left: 13.3125%
    +tablet
      padding-left: 0

  .left-side
    width: 50%
    background: #34495E

  .left-side-light
    background: #ECF0F1

  .menu
    text-align: center
    position: relative
    z-index: 1001

  .menu-list
    padding: 0
    margin: 0

  .menu-list-dark
    .menu-item
      .menu-link, .menu-list-dark .menu-item .menu-link:hover:before
        color: #34495E

  .menu-item
    display: inline-block
    margin-left: 40px
    &:first-child
      margin-left: 0

  .menu-link
    font: bold 12px/15px 'Merriweather Sans', Tahoma, serif
    letter-spacing: 1.2px
    text-transform: uppercase
    color: #ECF0F1
    text-decoration: none
    position: relative

  .menu-link:hover:before, .selected:before
    content: ''
    position: absolute
    width: 44px
    height: 3px
    top: calc(50% - 2px)
    left: calc(50% - 22px)
    transform: rotate(-45deg)
    background: #FFFFFF
    text-decoration: underline

  .menu-list-dark .menu-link:hover:before, .menu-list-dark .selected-dark:before
    content: ''
    position: absolute
    width: 44px
    height: 3px
    top: calc(50% - 2px)
    left: calc(50% - 22px)
    transform: rotate(-45deg)
    background: #34495E
    text-decoration: underline

  .social-list
    position: relative
    z-index: 999
    padding: 0
    text-align: center
    margin: 0
    .social-item
      .social-link
        +tablet
          .about &
            border-color: #34495E
        .fab
          +tablet
            .about &
              color: #34495E

  .social-item
    display: inline-block
    margin-left: 22.5px

  .social-item
    &:first-child
      margin-left: 0

  .social-link
    display: block
    width: 23px
    height: 23px
    text-align: center
    border-radius: 50%
    border: 2px solid #ECF0F1
    text-decoration: none
    .fab
      color: #ECF0F1
      font-size: 14px
      line-height: 23px

  .social-list-dark
    .social-item
      .social-link
        border-color: #34495E
        +tablet
          .index &
            border-color: #ECF0F1
          .product &
            border-color: #ECF0F1
          .contacts &
            border-color: #34495E
        .fab
          color: #34495E
          +tablet
            .index &
              color: #ECF0F1
            .product &
              color: #ECF0F1
            .contacts &
              color: #34495E

  .social-list-dark
    .social-item
      .social-link
        &:hover
          .fab
            color: darkred

  .social-link
    &:hover
      .fab
        color: darkred

  .left-side-padding
    padding-left: 8.875%

</style>
