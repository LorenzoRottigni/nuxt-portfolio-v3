<template lang="pug">
footer
    .container-fluid
        .row
            .col-4.bg-dark-deep.footer-left.p-2.pt-3.shadow-lg
                ul.mb-0.list-unstyled.d-flex.justify-content-around.align-items-center.d-md-none
                    li
                        i.fab.fa-linkedin.fa-2x
                    li
                        i.fab.fa-instagram.fa-2x
                h5.mb-0.text-center.d-none.d-md-block Designed with
                    span.text-coral.mx-1 &hearts;
                    | by 
                    span.fw-bold.text-yellow.ml-1 Lorenzo Rottigni
            .col-4.offset-4.bg-dark-deep.footer-right.p-2.pt-3.text-right.shadow-lg
                ul.mb-0.list-unstyled.d-flex.justify-content-around.align-items-center.text-secondary
                    li
                        a.text-yellow(href="#") Report a bug
                    li.d-none.d-md-block
                        i.fab.fa-linkedin.fa-2x
                    li.d-none.d-md-block
                        i.fab.fa-instagram.fa-2x
                    li
                        i.fab.fa-facebook.fa-2x
                    li
                        i.fab.fa-github.fa-2x
                    li.text-yellow
                        i.fas.fa-mail-bulk.fa-2x
                    
</template>

<script>
export default {
    
}
</script>

<style lang="sass" scoped>
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