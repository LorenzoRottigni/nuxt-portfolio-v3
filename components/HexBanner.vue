<template lang="pug">
.hex-container.d-flex.align-items-center.justify-content-around
    h5.text-nowrap.text-dark-deep.mb-0 {{textContent}}
    lord-icon.flex-shrink-0(
      src="https://cdn.lordicon.com/nobciafz.json"
      trigger="loop"
      colors="primary:#202020,secondary:#2e2e2e"
      style="width:80px;height:80px"
    )
</template>

<script>
export default {
    props: {
        textContent : String
    }
}
</script>

<style lang="sass" scoped>
.hex-container
    display: inline-block
    width: fit-content
    padding: 0.4rem
    clip-path: polygon(0 0, 95% 0, 100% 50%, 95% 100%, 0 100%, 0 50%)
    overflow: hidden
</style>
