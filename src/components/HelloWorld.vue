<template>
  <div>
    <div
      id="step1tour"
      ref="childElement"
      style="width: 500px; height: 500px; margin: 0 auto;"
    ></div>
    <v-tour name="tour" :steps="steps" />
  </div>
</template>

<script>
import anime1 from "../../public/images/anime1.json";
import lottie from "lottie-web";

export default {
  name: "HelloWorld",

  data() {
    return {
      file: anime1,
      steps: [
        {
          target: "step1tour",
          content: "testing"
        }
      ]
    };
  },

  mounted() {
    const element1 = this.$refs.childElement;
    console.log("jkj", this.$refs.childElement);
    lottie.loadAnimation({
      container: element1,
      renderer: "svg",
      loop: true,
      autoplay: true,
      animationData: this.file
    });
    this.$tours["tour"].start();
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped></style>
