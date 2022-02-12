<template lang="pug">
.container-fluid.overflow-auto

  ///////////////
  // FIRST ROW //
  ///////////////
  section#hero-section.row
    .col-10.offset-1.col-xl-8.offset-xl-2.px-0
      .container.h-100.d-flex.align-items-center.flex-wrap
        .col-8.offset-2.col-lg-6.offset-lg-0.px-0
          //HERO IMAGE
          #hero-polygon-image
            .hero-image-overlay

        //////////////////////////////
        // DESKTOP HERO CONTENT ROW //
        //////////////////////////////
        .col-12.col-lg-6.px-0.d-block.d-lg-none
          #hero-content-mobile.d-flex.flex-column.align-items-center.justify-content-center.py-3
            h2.text-primary.text-nowrap.mb-0 LORENZO ROTTIGNI
            .d-flex.align-items-center.justify-content-center
              .d-flex.flex-column.border-top.border-bottom.border-primary.px-2
                lord-icon(
                  src="https://cdn.lordicon.com/anihkfxp.json"
                  trigger="loop"
                  colors="primary:#ff6f28,secondary:#ffffff"
                  style="width:65px;height:65px"
                )
                h6.text-white.text-center LR Term
              .d-none.d-md-flex.flex-column.border-top.border-bottom.border-primary.px-2
                lord-icon(
                  src="https://cdn.lordicon.com/dtgezzsi.json"
                  trigger="loop"
                  colors="primary:#ff6f28,secondary:#ffffff"
                  style="width:65px;height:65px"
                )
                h6.text-white.text-center Coding
              .border-left.border-right.border-primary.p-3.my-3.bg-dark-deep
                LogoLR
              .d-none.d-md-flex.flex-column.border-top.border-bottom.border-primary.px-2
                lord-icon(
                  src="https://cdn.lordicon.com/nocovwne.json"
                  trigger="loop"
                  colors="primary:#ff6f28,secondary:#ffffff"
                  style="width:65px;height:65px"
                )
                h6.text-white.text-center CV

              .d-flex.flex-column.border-top.border-bottom.border-primary.px-2
                lord-icon(
                  src="https://cdn.lordicon.com/ochimkct.json"
                  trigger="loop"
                  colors="primary:#ff6f28,secondary:#ffffff"
                  style="width:65px;height:65px"
                )
                h6.text-white.text-center Repos
            h4.text-white.text-nowrap.mb-0 Full-Stack Web Developer
        //////////////////////////////
        // DESKTOP HERO CONTENT ROW //
        //////////////////////////////
        .col-12.col-lg-6.px-0.d-none.d-lg-block
          #hero-content-desktop.border-primary.border-bottom.p-0.d-flex.align-items-start.justify-content-center
            //ROLLING LOGO
            .logo-svg.p-2
              LogoLR
            .w-100.h-100.d-flex.flex-column.justify-content-start.justify-content-lg-around
              h1.text-center.border-bottom.border-primary.py-3.mb-0 LORENZO ROTTIGNI
              .bg-dark-deep.flex-grow-1.d-flex.flex-column.align-items-start.justify-content-around.p-3.border-left.border-right.border-primary
                //HEX BANNER
                HexBanner.bg-primary.text-dark.ml-n3.mt-2.shadow-lg(
                    textContent="FULL-STACK WEB DEVELOPER"
                )
                //HERO PARAGRAPHS
                .text-container.text-white.py-3.d-none.d-lg-block
                  p.mb-1 Welcome to my web portfolio!
                  p.mb-1 You can play at my portfolio using the top, left, right, and bottom pivotal buttons.
                  p.mb-1 The radar on the left of your screen will track your position around the map, you can look at routes nearby and reach them by clicking its icon

              //HERO FOOTER
              .hero-footer.bg-dark-deep.border.border-primary.d-flex.justify-content-end.justify-content-lg-start
                .w-75.d-flex.py-3.justify-content-end.justify-content-lg-around
                  a.px-3.text-decoration-none.d-none.d-md-block(href="#Terminal")
                    button.btn.btn-primary Terminal
                  span.d-none.d-lg-block
                    a.text-decoration-none(href="#About")
                      button.btn.btn-outline-primary About




  ////////////////
  // SECOND ROW //
  ////////////////
  section#Terminal.row
    .col-10.offset-1.col-xl-8.offset-xl-2.border
      .d-flex.justify-content-center.align-items-center.h-100.rounded
        .w-50.h-75.p-3.bg-dark.d-flex.align-items-center.border.border-primary.shadow-lg
          ul.w-100.h-100.bg-primary.text-dark.h-75.mb-0.d-flex.flex-column.justify-content-center
            li
              button.btn Help
            li
              button.btn Routing
            li
              button.btn date
            li
              button.btn repo
            li
              button.btn video
        .w-50.h-75.p-3.bg-dark.d-flex.align-items-center.border.border-primary.shadow-lg
          Terminal.bg-light.w-100.h-100.p-3(
            welcomeMessage="Welcome to my CLI",
            prompt="~guest $",

          )

  ///////////////
  // THIRD ROW //
  ///////////////
  section#About.row
    .col-10.offset-1.col-xl-8.offset-xl-2.border
        h1 3rd row
</template>

<script>
import Terminal from 'primevue/terminal'
import TerminalService from 'primevue/terminalservice'

export default {
  components: { Terminal },
  methods:{
    scrollTop(){
      if(process.browser){
        const firstRow = document.getElementById('hero-section')
        firstRow.scrollIntoView()
        //scrollableContainer.scrollTop = document.documentElement.clientHeight * 0.2
        //document.documentElement.clientHeight * 0.03
      }
    }
  },
  mounted(){
    this.scrollTop()
  }
}
</script>

<style lang="sass" scoped>

///////////////////////////
// SCROLLING 100VH LAYOT //
///////////////////////////

.container-fluid
  max-height: 100vh
  scroll-behavior: smooth
  .row
    height: 100vh
    padding: 12.5vh 0
    transition: 1.5s

/////////////////
//INDEX LAYOUT //
/////////////////


// POLYGON HERO IMAGE
#hero-polygon-image
  background-color: rgba(0,0,0,0.2)
  height: 35vh
  width: auto
  position: relative
  margin: 0 auto
  clip-path: polygon(10% 0, 90% 0, 100% 10%, 100% 90%, 90% 100%, 10% 100%, 0 90%, 0 10%)
  .hero-image-overlay
    position: absolute
    top: 0
    left: 0
    right: 0
    bottom: 0
    transition: all 0.5s
    background-image: url('~static/profile_image.png')
    background-size: cover
    background-repeat: no-repeat
    background-position: center

// HERO TEXT CONTENT
#hero-content-desktop
  //height: 55vh
  height: 55vh
  width: 100%
  position: relative

  //hero name
  h1
    background-color: rgba(map-get($theme-colors, "primary"), 0.5)
    color: $dark-deep
    font-weight: bolder !important
    font-size: 34px

  .hero-footer
    border-bottom-right-radius: 30px

  //rolling logo LR design
  .logo-svg
    position: absolute
    bottom: 0
    right: 0
    transform: translate(35%,20%)
    background-color: $dark-deep
    border: double 7px $coral
    border-radius: 50%



@media screen and (min-width: 992px)
  // LG BREAKPOINT HERO IMAGE
  #hero-polygon-image
    height: 55vh
    clip-path: polygon(25% 0%, 100% 0, 100% 50%, 100% 100%, 25% 100%, 0% 50%)
    width: 100%
    .hero-image-overlay
      position: absolute
      background-position: right
</style>
