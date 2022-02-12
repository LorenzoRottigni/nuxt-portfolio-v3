<template lang="pug">
.container-fluid.overflow-auto

  ///////////////
  // FIRST ROW //
  ///////////////
  section#hero-section.row
    .col-10.offset-1.col-xl-8.offset-xl-2.px-0
      .container.h-100.d-flex.align-items-center.flex-wrap
        .col-12.col-sm-8.offset-sm-2.col-lg-6.offset-lg-0.px-0
          //HERO IMAGE
          #hero-polygon-image
            .hero-image-overlay




        //////////////////////////////
        // MOBILE HERO CONTENT ROW //
        //////////////////////////////
        .col-12.col-lg-6.px-0.d-block.d-lg-none
          #hero-content-mobile.d-flex.flex-column.align-items-center.justify-content-center.py-3
            h2.text-primary.text-nowrap LORENZO ROTTIGNI
            h5.text-white.text-nowrap.mb-0 Full-Stack Web Developer
            .d-flex.align-items-center.justify-content-center
              .hero-lord-icon.border-top.border-bottom.border-primary.px-2
                a.d-flex.flex-column(href="#Terminal")
                  lord-icon(
                    src="https://cdn.lordicon.com/anihkfxp.json"
                    trigger="loop"
                    colors="primary:#ff6f28,secondary:#ffffff"
                    style="width:65px;height:65px"
                  )
                  h6.text-white.text-center LR Term
              .hero-lord-icon.d-none.d-sm-flex.flex-column.border-top.border-bottom.border-primary.px-2
                a.d-flex.flex-column(href="#About")
                  lord-icon(
                      src="https://cdn.lordicon.com/ngcezuqf.json"
                      trigger="loop"
                      colors="primary:#ff6f28,secondary:#ffffff"
                      style="width:65px;height:65px"
                    )
                  h6.text-white.text-center About
              .border-left.border-right.border-primary.p-3.my-3.bg-dark-deep
                LogoLR
              .hero-lord-icon.d-none.d-sm-flex.flex-column.border-top.border-bottom.border-primary.px-2
                nuxt-link.d-flex.flex-column(to="/cv")
                  lord-icon(
                    src="https://cdn.lordicon.com/nocovwne.json"
                    trigger="loop"
                    colors="primary:#ff6f28,secondary:#ffffff"
                    style="width:65px;height:65px"
                  )
                  h6.text-white.text-center CV

              .hero-lord-icon.d-flex.flex-column.border-top.border-bottom.border-primary.px-2
                nuxt-link.d-flex.flex-column(to="/github")
                  lord-icon(
                    src="https://cdn.lordicon.com/ochimkct.json"
                    trigger="loop"
                    colors="primary:#ff6f28,secondary:#ffffff"
                    style="width:65px;height:65px"
                  )
                  h6.text-white.text-center Repos
            





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
                  a.px-2.text-decoration-none.d-flex.align-items-center(href="#Terminal")
                    lord-icon(
                      src="https://cdn.lordicon.com/anihkfxp.json"
                      trigger="loop"
                      colors="primary:#ff6f28,secondary:#ffffff"
                      style="width:65px;height:65px"
                    )
                    h6.text-white.text-center.text-nowrap.mb-0 LR Term

                  a.px-2.text-decoration-none.d-flex.align-items-center(href="#About")
                    lord-icon(
                      src="https://cdn.lordicon.com/ngcezuqf.json"
                      trigger="loop"
                      colors="primary:#ff6f28,secondary:#ffffff"
                      style="width:65px;height:65px"
                    )
                    h6.text-white.text-center.text-nowrap.mb-0 About




  ////////////////
  // TERMINAL ROW //
  ////////////////
  section#Terminal.row.align-items-center
    .col-10.offset-1.col-lg-5.offset-lg-0.order-lg-2
      Terminal.bg-light.w-100.p-3.mt-3(
            welcomeMessage="Welcome to my CLI",
            prompt="~guest $",
          )
    nav.col-12.col-lg-5.order-lg-1.offset-lg-1
      ul.list-unstyled.bg-dark-deep.text-dark.mb-0.d-flex.flex-column.mt-3
        li.text-warning.d-flex.align-items-center.py-2.border-bottom.border-primary
          lord-icon.mx-3(
            src="https://cdn.lordicon.com/vlupvdhl.json"
            trigger="loop",
            colors="primary:#ff6f28,secondary:#ffffff",
            style="width:30px;height:30px",
          )
          h6.mb-0 Help
        li.text-warning.d-flex.align-items-center.py-2.border-bottom.border-primary
          lord-icon.mx-3(
            src="https://cdn.lordicon.com/vlupvdhl.json"
            trigger="loop",
            colors="primary:#ff6f28,secondary:#ffffff",
            style="width:30px;height:30px",
          )
          h6.mb-0 Routing
        li.text-warning.d-flex.align-items-center.py-2.border-bottom.border-primary
          lord-icon.mx-3(
            src="https://cdn.lordicon.com/vlupvdhl.json"
            trigger="loop",
            colors="primary:#ff6f28,secondary:#ffffff",
            style="width:30px;height:30px",
          )
          h6.mb-0 repo
        li.text-warning.d-flex.align-items-center.py-2.border-bottom.border-primary
          lord-icon.mx-3(
            src="https://cdn.lordicon.com/vlupvdhl.json"
            trigger="loop",
            colors="primary:#ff6f28,secondary:#ffffff",
            style="width:30px;height:30px",
          )
          h6.mb-0 video
 





  ///////////////
  // THIRD ROW //
  ///////////////
  section#About.row.overflow-auto.align-items-center
    .col-10.offset-1.mt-3
      .d-flex.flex-column.align-items-center.h-100
        h1.text-center.text-primary ABOUT ME 
        .paragraph-container.text-white.mt-3
          p I am a Web Developer and  I started my path in the IT approaching it as a game, a quest based videogame.
          p Whenever a project works well or whenever a new skill is learnt, a new task gets completed: the tasks I complete, together, are composing my game profile or better, my developer profile.
          p I always loved that kind of videogame, the more you play and the more you improve yourself, your profile aspect and the people you play with.
          p This is just a beautiful free-to-play game that never ends, day by day.
        a.d-flex.align-items-center.mt-3(href="#hero-section")
          lord-icon(
            src="https://cdn.lordicon.com/gmzxduhd.json"
            trigger="loop"
            colors="primary:#ff6f28,secondary:#ffffff"
            style="width:65px;height:65px"
          )
          h6.mb-0.mx-3 Home
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
  height: 45vh
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

//HERO CONTENT MOBILE
  
.hero-lord-icon
  background-color: rgba(0,0,0,0.2)



// HERO TEXT CONTENT
#hero-content-desktop
  //height: 55vh
  height: 60vh
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
    height: 60vh
    clip-path: polygon(25% 0%, 100% 0, 100% 50%, 100% 100%, 25% 100%, 0% 50%)
    width: 100%
    .hero-image-overlay
      position: absolute
      background-position: right
</style>
