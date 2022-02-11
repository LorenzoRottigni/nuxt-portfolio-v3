<template lang="pug">
.clip-path-circle-hover(
    :class="[(size === 'xs') ? 'w-xs' : '', (size === 'md') ? 'w-md' : '', (size === 'lg') ? 'w-lg' : '', (size != 'xs' && size != 'md' && size != 'lg') ? 'w-md' : '']"
)
    button(
        :style="getColor"
    ) {{textContent}}
</template>

<script>
export default {
    props:{
        textContent: String,
        size: String,
        color: String
    },
    data(){
        return{
            styles : {
                backgroundColor : '',
                color: '',
                padding: '',
            }
        }
    },
    computed: {
        getColor(){
            //COLORS
            const DARK = '#202020'
            const LIGHT = '#FFFFFF'
            const CORAL = '#ff6f28'
            const YELLOW = '#F9E79F'
            //PADDING
            const PY_XS = '0.5rem 0'
            const PY_MD = '1rem 0'
            const PY_LG = '1rem 0'

            const styles = this.styles

            switch(this.color){
                case 'coral':
                    styles.backgroundColor = CORAL
                    styles.color = LIGHT
                    break;
                case 'dark':
                    styles.backgroundColor = DARK
                    styles.color = LIGHT
                    break;
                case 'yellow':
                    styles.backgroundColor = YELLOW
                    styles.color = DARK
                    break;
                case 'light':
                    styles.backgroundColor = LIGHT
                    styles.color = DARK
                    break;
                default:
                    styles.backgroundColor = CORAL
                    styles.color = LIGHT
            }

            switch(this.size){
                case 'xs':
                    styles.padding = PY_XS
                    styles.fontSize = '14px'
                    break;
                case 'md':
                    styles.padding = PY_MD
                    styles.fontSize = '18px'
                    break;
                case 'lg':
                    styles.padding = PY_LG
                    styles.fontSize = '20px'
                    break;
                default:
                    styles.padding = PY_MD
                    styles.fontSize = '18px'
            }

            return styles
        }
    }
}
</script>

<style lang="sass" scoped>
.w-xs
    width: 100px
.w-md
    width: 150px
.w-lg
    width: 200px

.clip-path-circle-hover
    //width: 200px
    margin: 0 auto
    transition: all 0.5s
    clip-path: circle(70%)
    &:hover
        clip-path: circle(50%)
        //rgba(31, 73, 125, 0.8)
        box-shadow: 12px 0 16px -4px $coral, -12px 0 8px -4px $coral
button
    display: inline-block
    position: relative
    color: #fff
    font-weight: 500
    font-size: 18px
    text-decoration: none
    text-transform: uppercase
    //padding: 1rem 5rem
    padding: 1rem 0
    width: 100%
    text-align: center
    border: none
    //clip-path: polygon(7% 0, 93% 0, 100% 50%, 93% 100%, 7% 100%, 0 50%)
    clip-path: polygon(7% 0, 93% 0, 100% 50%, 93% 100%, 7% 100%, 0 50%)
    background-color: $coral
    //background-image: radial-gradient(200% 70% at center 20%, rgba(48,44,45,1) -30%, rgba(50,46,47,1) 49%, rgba(22,18,19,1) 50%, rgba(22,18,19,1) 150%)
    background-repeat: no-repeat
    transition: all 1s
    &:hover 
        //background-position-y: -50px
        //clip-path: polygon(0 0, 20% 0%, 80% 0%, 100% 100%, 0% 100%, 0 0)
        color: $dark-deep
        font-weight: bold
    &:active 
        transform: scale(0.99)  
</style>












