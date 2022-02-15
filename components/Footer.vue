<template lang="pug">
footer
    .container-fluid
        .row.d-sm-none
            .col-8.bg-dark-deep.footer-left.p-2.shadow-lg
                ul.mb-0.list-unstyled.d-flex.justify-content-around.align-items-center.h-100.text-warning
                    //li
                        a.text-yellow(href="#") Report a bug
                    li.px-3
                        a(href="https://www.linkedin.com/in/lorenzo-rottigni-ba402b222")
                            i.fab.fa-linkedin.fa-lg
                    li.px-3.border-left.border-warning
                        a(href="https://www.instagram.com/lorenzorottigni/")
                        i.fab.fa-instagram.fa-lg
                    li.px-3.border-left.border-warning
                        a(href="#")
                            i.fab.fa-facebook.fa-lg
                    li.px-3.border-left.border-warning
                        a(href="https://github.com/LorenzoRottigni")
                            i.fab.fa-github.fa-lg
                        
            .col-3.offset-1.bg-dark-deep.footer-right.p-2.shadow-lg
                .w-100.d-flex.justify-content-center
                    Sidebar.p-sidebar-lg.bg-primary.text-dark(
                        :visible.sync='modalStatus',
                        position="full",
                        showCloseIcon=NULL
                    )

                        nav
                            ul
                                li(v-for="(route, index) in getVueRoutes") {{route.name}}
                            button.btn(@click='modalStatus = false')
                    //Button.btn(@click='modalStatus = true')
                    Button(label="menu" iconPos="right" icon="pi pi-check" @click="modalStatus = true")
                        //lord-icon(
                            src="https://cdn.lordicon.com/phtfmmnb.json"
                            trigger="loop"
                            colors="primary:#ff6f28,secondary:#ffffff"
                            style="width:40px;height:40px"
                            )
        .row.d-none.d-sm-flex
            .col-4.bg-dark-deep.footer-left.p-2.shadow-lg.d-flex.align-items-center.justify-content-center
                h5.mb-0.text-center.text-white Designed with
                    span.text-coral.mx-1
                        lord-icon(
                            src="https://cdn.lordicon.com/rjzlnunf.json"
                            trigger="loop"
                            colors="primary:#ff6f28,secondary:#ffffff"
                            style="width:30px;height:30px"
                        )
                    | by 
                    span.text-yellow.ml-1 Lorenzo Rottigni
            .col-4.offset-4.bg-dark-deep.footer-right.p-2.pt-3.shadow-lg
                ul.mb-0.list-unstyled.d-flex.justify-content-center.align-items-center.h-100.text-warning
                    //li
                        a.text-yellow(href="#") Report a bug
                    li.w-100.border.border-primary
                    li.px-3
                        a(href="https://www.linkedin.com/in/lorenzo-rottigni-ba402b222")
                            i.fab.fa-linkedin.fa-2x
                    li.px-3.border-left.border-primary
                        a(href="https://www.instagram.com/lorenzorottigni/")
                        i.fab.fa-instagram.fa-2x
                    li.px-3.border-left.border-primary
                        a(href="#")
                            i.fab.fa-facebook.fa-2x
                    li.px-3.border-left.border-primary
                        a(href="https://github.com/LorenzoRottigni")
                            i.fab.fa-github.fa-2x
                    li.w-100.border.border-primary
</template>

<script>
import Sidebar from 'primevue/sidebar'
import Button from 'primevue/button'

export default {
    radarDisplay : false,
    data(){
        return {
            modalStatus: false
        }
    },
    computed: {
        getVueRoutes(){
            console.log(this.$router)
            return this.$router.options.routes
        }
    },
    components: {Sidebar, Button}
}

</script>

<style lang="sass" scoped>
h5
    font-weight: normal
footer
    z-index: 99
    position: absolute
    bottom: -3px
    left: -3px
    right: -3px
    .footer-left
        border-top-right-radius: 30px
        border-top: solid 1px $coral
        border-right: solid 1px $coral
        color: #ffffff
    .footer-right
        border-top-left-radius: 30px
        border-top: solid 1px $coral
        border-left: solid 1px $coral
    //background-color: $coral
</style>