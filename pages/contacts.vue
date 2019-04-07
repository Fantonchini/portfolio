<template>
  <main class="contacts-container">
    <div class="contacts-left left-side-padding">
      <form class="contacts-form" onsubmit="validate(event)">
        <input id="name" class="forms" type="text" name="" placeholder="Name">
        <input id="email" class="forms" type="email" name="" placeholder="E-mail">
        <input id="telephone" class="forms" type="tel" name="" placeholder="Number">
        <textarea id="message" class="forms text-area" placeholder="Message"></textarea>
        <button class="forms form-submit">
          <span class="form-submit-text">Submit<img class="submit-img" src="@/static/Paper-plane.svg" alt=""></span>

        </button>
      </form>
    </div>
    <div class="contacts-right">
      <div id="map"></div>
    </div>
  </main>
</template>

<script>
export default {
    name: "contacts",
    props: {

    },
  data() { //local variables
      return {

      }
  },
  mounted() {
    this.$axios
      .get('https://api-maps.yandex.ru/2.1/?apikey=b0a9c194-4603-49d6-ba95-61be620cf275&lang=ru_RU')
      .then(() => {
        const ymaps = window.ymaps
        ymaps.ready(() => {
          new ymaps.Map("map", {
            center: [44.72561836, 37.76416813],
            zoom: 12
          })
        })
      })
  },
  computed: {

  },
  methods: {

  }
}
</script>

<style lang="sass" scoped>
  .contacts-container
    width: 100%
    flex-grow: 1
    display: flex
    flex-direction: row

  .contacts-left
    width: 50%
    display: flex
    flex-direction: row
    justify-content: center
    align-items: center

  .contacts-form
    margin: 0 auto
    display: flex
    flex-direction: column
    justify-content: center
    width: 350px
    overflow: visible
  .left-side-padding
    padding-left: 8.875%
  .forms
    padding-left: 25px
    font: bold 14px/55px 'Open Sans', serif
    color: #ECF0F1
    background: #34495E
    mix-blend-mode: normal
    opacity: 0.9
    border: 0
    border-radius: 27px
    margin-bottom: 35px

  .forms::placeholder
    opacity: 1
    color: #ECF0F1

  .form-submit
    background: #ECF0F1
    color: #34495E
    border: 2px solid #34495E
    cursor: pointer

  .text-area
    height: 168px
    resize: none

  .forms:last-child
    margin-bottom: 0

  .map-background
    background: #ECF0F1 url(../static/map.png) right center no-repeat

  .forms:focus, a:focus
    outline: none
  .contacts-right
    width: 50%
    position: relative
  .form-submit-text
    position: relative
  .submit-img
    top: -10%
    left: 86%
    position: absolute
  #map
    z-index: 0
    top: 0%
    left: 0%
    right: 0%
    bottom: 0%
    margin-top: -75px
    position: absolute
    width: 100%
    height: 820px

</style>
