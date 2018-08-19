<template>
    <div class="container">
        <!-- <h1>Single Element Animations</h1>
        <hr/>
        <button class="btn btn-primary" @click="show = !show">Click</button>
        <br/><br/> -->
        <!-- fade is setup as one type of transition in css -->
        <!-- <transition name="fade">
            <div v-if="show" class="alert alert-info">This is some info</div>
        </transition> -->

        <!-- slide has been setup in css - you can have any name -->
        <!-- you can apply appear directive to play animation on load as well -->
        <!-- <transition name="slide" appear>
            <div v-if="show" class="alert alert-info">This is some info</div>
        </transition> -->

        <!-- you can also try animated.css library -->
        <!-- <transition 
            appear
            enter-active-class="animated bounce"
            leave-active-class="animated bounce"
        >
            <div style="width:20%" v-if="show" class="alert alert-info">This is some info</div>
        </transition> -->

        <!-- multiple elements where new one gets faded in before the old one fades out resulting in jumping effect -->
        <!-- mode as out in means let the element fade out and then fade in new one -->
        <!-- for multiple element you need to give key when only one of them will be visible on the page -->
        <!-- <transition name="slide" appear mode="out-in">
            <div v-if="show" class="alert alert-info" key="info">This is some info</div>
            <div v-else class="alert alert-warning" key="warning">This is some warning</div>
        </transition> -->
        <multiple/>
    </div>
</template>

<script>
import Multiple from "./components/Multiple.vue";

export default {
  data() {
    return {
      show: true
    };
  },
  components: {
    Multiple
  }
};
</script>

<style>
.fade-enter {
  opacity: 0;
}

.fade-enter-active {
  transition: opacity 0.5s;
}

.fader-leave {
}

.fade-leave-active {
  transition: opacity 0.5s;
  opacity: 0;
}

.slide-enter {
  transform: translateY(50px);
  opacity: 0;
}

.slide-enter-active {
  transition: all 0.5s;
}

.slide-leave {
}

.slide-leave-active {
  transition: all 0.5s;
  transform: translateY(50px);
  opacity: 0;
}
</style>
