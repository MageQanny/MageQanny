<template>
  <div id="console">
    <transition name="typing-text">
      <h3>
        <span id="prompt">
          mageqanny@netlify-app:$
        </span>
        <span id="typed-text">
          {{introText}}
        </span>
      </h3>
    </transition>
  </div>
</template>

<script>
import { 
  ref, 
  // onMounted 
} from "vue";

export default {
    setup(){
    
      const introText = ref('./mageqanny');

      // onMounted();

      return {
        introText, 
      }
    }
};
</script>


<style scoped>

#console{
  font-family: 'Source Code Pro', monospace;
  font-size: 25px;
  font-weight: 600;
  width: 100%;
  height: 100vh;
  background-color: black;
}
h3{
  margin: 0;
}
#prompt{
  color: green;
}
#typed-text{
  color: greenyellow;
}
</style>
