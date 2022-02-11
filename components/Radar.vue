<template lang="pug">
#radar.bg-dark-deep.flex-wrap(
    :style="{ width: 'calc(' + boxSize * 3 + 'vw + 3px)', height : 'calc(' + boxSize * 3 + 'vw )' }"
)
    //RadarCircles(
        bozSize="boxSize"
        )
    .radar-box.border-yellow(
        v-for="(route, index) in radarRoutes",
        :key="'route-'+index",
        @click="changeRoute(route.name)",
        :style="{ width: boxSize + 'vw', height: boxSize + 'vw'}"
    )
        .h-100.d-flex.flex-column.align-items-center.justify-content-center(
            v-if="route.name != getActiveVueRouteName"
        )
            span.text-secondary(v-html="route.template")
            span.text-secondary {{route.name}}
    #user-icon.d-flex.flex-column.align-items-center.justify-content-center(
        :style="{ left: 'calc( '+ boxSize + 'vw * '+ radarX + ')', top: 'calc( ' + boxSize + 'vw * '+ radarY + ')', width: boxSize + 'vw', height: boxSize + 'vw'}"
    )
        //i.fas.fa-street-view.text-yellow.fa-2x
        lord-icon(
          src="https://cdn.lordicon.com/ibgjiwvi.json",
          trigger="loop",
          colors="primary:#F9E79F,secondary:#6c757d",
          stroke="80",
          :style="{ width: boxSize+'vw', height: boxSize+'vw' }",
        )
</template>

<script>


export default {
    data() {
        return {
            radarX: undefined,
            radarY: undefined,
            radarRoutes: [
                {
                    id: 0,
                    name: "contacts",
                    template: "<i class=\"far fa-id-badge fa-lg\"></i>",
                    radarX: 0,
                    radarY: 0
                },
                {
                    id: 1,
                    name: "skills",
                    template: "<i class=\"fas fa-cloud fa-lg\"></i>",
                    radarX: 1,
                    radarY: 0
                },
                {
                    id: 2,
                    name: "exp",
                    template: "<i class=\"fas fa-graduation-cap fa-lg\"></i>",
                    radarX: 2,
                    radarY: 0
                },
                {
                    id: 3,
                    name: "cv",
                    template: "<i class=\"far fa-file-alt fa-lg\"></i>",
                    radarX: 0,
                    radarY: 1
                },
                {
                    id: 4,
                    name: "index",
                    template: "<i class=\"fas fa-home fa-lg\"></i>",
                    radarX: 1,
                    radarY: 1
                },
                {
                    id: 5,
                    name: "portfolio",
                    template: "<i class=\"fas fa-code fa-lg\"></i>",
                    radarX: 2,
                    radarY: 1
                },
                {
                    id: 6,
                    name: "github",
                    template: "<i class=\"fab fa-github fa-lg\"></i>",
                    radarX: 0,
                    radarY: 2
                },
                {
                    id: 7,
                    name: "work",
                    template: "<i class=\"fab fa-vimeo-v fa-lg\"></i>",
                    radarX: 1,
                    radarY: 2
                },
                {
                    id: 8,
                    name: "blog",
                    template: "<i class=\"fas fa-th-list fa-lg\"></i>",
                    radarX: 2,
                    radarY: 2
                }
            ],
            radarActiveIndex: 4,
            boxSize: 5
        };
    },
    methods: {
        /**
         * @description updates user coordinates in the radar
         */
        movePown() {
            this.radarX = this.radarRoutes[this.radarActiveIndex].radarX;
            this.radarY = this.radarRoutes[this.radarActiveIndex].radarY;
        },
        emitRoutes(route_name) {
            //find the radarActiveRoute using VueRouter route name as key
            const activeRadarRoute = this.radarRoutes.filter(route => route.name === route_name);
            //get the radarActiveRouteId
            this.radarActiveIndex = activeRadarRoute[0].id;
            //move the user pown in the radar
            this.movePown();
            //emit the name of the next route
            this.$emit("radarNext", this.getNextActiveRoute);
            //emit the name of the previous route
            this.$emit("radarPrevious", this.getPreviousActiveRoute);
            //emit the name of the top route
            this.$emit("radarTop", this.getTopActiveRoute);
            //emit the name of the bottom route
            this.$emit("radarBottom", this.getBottomActiveRoute);
            //emit the selected id
            this.$emit("radarActiveIndex", activeRadarRoute[0].id);
        },
        changeRoute(route_name) {
            this.$router.push({ name: route_name });
        }
    },
    computed: {
        /**
         * @description returns VueRouter active route
         */
        getActiveVueRouteName() {
            return this.$route.name;
        },
        /**
         * @description if has a next route returns its name else returns undefined
         */
        getNextActiveRoute() {
            const nextRoute = this.radarRoutes[this.radarActiveIndex + 1];
            if (nextRoute)
                return nextRoute.name;
            else
                return undefined;
        },
        /**
         * @description if has a previous route returns its name else returns undefined
         */
        getPreviousActiveRoute() {
            const nextRoute = this.radarRoutes[this.radarActiveIndex - 1];
            if (nextRoute)
                return nextRoute.name;
            else
                return undefined;
        },
        /**
         * @description if has a top route returns its name else returns undefined
         */
        getTopActiveRoute() {
            const nextRoute = this.radarRoutes[this.radarActiveIndex - 3];
            if (nextRoute)
                return nextRoute.name;
            else
                return undefined;
        },
        /**
         * @description if has a bottom route returns its name else returns undefined
         */
        getBottomActiveRoute() {
            const nextRoute = this.radarRoutes[this.radarActiveIndex + 3];
            if (nextRoute)
                return nextRoute.name;
            else
                return undefined;
        }
    },
    watch: {
        /**
         * @description at route change, set active ID of local radarRoutes array and move user pown
         */
        getActiveVueRouteName: {
            immediate: true,
            handler(val, old) {
                this.emitRoutes(val);
            }
        }
    },
    created() {
        if (process.browser) {
            const clientWidth = window.innerWidth;
            switch (true) {
                case (clientWidth <= 992):
                    this.boxSize = 7;
                    break;
                case (clientWidth <= 1200):
                    this.boxSize = 6;
                    break;
                default:
                    this.boxSize = 5;
            }
        }
        // move the user pown in the radar
        this.movePown();
    }
}
</script>

<style lang="sass" scoped>
@keyframes blink
    0%
        opacity: 1
    50%
        opacity: 0
    100%
        opacity: 1
@keyframes rotate
    0%
        transform: rotate(0)
        opacity: 0.2
    100%
        transform: rotate(360deg)
        opacity: 0.2

#radar
    position: absolute
    top: 0
    left: 0
    //height: 15vw
    //width: calc(15vw + 3px)
    border-bottom: solid 3px $coral
    border-right: solid 3px $coral
    border-bottom-right-radius: 2rem
    overflow: hidden
    &::before
        content: ''
        position: absolute
        top: 50%
        transform: translateY(-50%)
        width: 200%
        left: -50%
        right: -50%
        border: solid 1px $yellow
        animation: rotate 6s infinite linear
    &::after
        content: ''
        position: absolute
        top: 0
        bottom: 0
        left: 0
        right: 0
        background-image: url('~static/radar-bg.svg')
        background-repeat: no-repeat
        background-size: cover
        animation: blink 1.5s infinite
    .radar-box
        z-index: 99
        //width: 5vw
        //height: 5vw
    #user-icon
        position: absolute
        //width: 5vw
        //height: 5vw
        transition: all 1s
        z-index: 99
</style>
