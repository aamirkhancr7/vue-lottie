<template>
    <div ref="childElement" style="width: 500px; height: 500px; margin: 0 auto;"></div>
</template>

<script>
    import anime1 from '../../public/images/anime1.json'
    import lottie from 'lottie-web'

    export default {
        name: "HelloWorld",

        data() {
            return {
                file: anime1
            }
        },

        mounted() {
            const element1 = this.$refs.childElement
            console.log('jkj', this.$refs.childElement)
            lottie.loadAnimation(
                {
                    container: element1,
                    renderer: 'svg',
                    loop: true,
                    autoplay: true,
                    animationData: this.file
                }
            )
        }

    };
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
