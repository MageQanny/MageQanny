<template>
  <div id="console">
    <transition-group name="typing-text">
      <h3 id="line-1" key="line1">
        <span class="prompt">
          mageqanny@netlify-app:$
        </span>
        <span class="typed-text">
          {{line1}}
        </span>
        <span :class="{blink: !viewLine2}" v-if="!viewLine2">_</span>
      </h3>
      <h3 id="line-2" v-if="viewLine2" key="line2">
        Error index.html not found. Return in a few days
      </h3>
      <h3 id="line-2" v-if="viewLine2" key="line3">
        <span class="prompt">
          mageqanny@netlify-app:$
        </span>
        <span class="typed-text blink">_</span>
      </h3>
    </transition-group>
  </div>
</template>

<script>
import { 
  ref, 
  onMounted 
} from "vue";

export default {
    setup(){
    
      const line1 = ref('');

      const text = './mageqanny';

      const viewLine2 = ref(false);

      function typing() {
        if (line1.value.length < text.length){
          line1.value += text.substring(line1.value.length, line1.value.length+1)
          setTimeout(typing, 100)
        }
        else {
          setTimeout(()=>{
            viewLine2.value = !viewLine2.value
          }, 1500)
          return
        }
      }

      onMounted(()=>{
        setTimeout(typing, 1500)
      });

      return {
        line1, viewLine2
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
.prompt{
  color: green;
}
.typed-text{
  color: greenyellow;
}
.blink{
  color: black;
  animation: blinking 1s steps(1) infinite;
}

@keyframes blinking {
  50%{
    color: greenyellow;
  }
}
</style>
