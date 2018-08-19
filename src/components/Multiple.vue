<template>
  <div class="container">
    <h1>Multiple Element Animations</h1>
    <hr/>
    <button class="btn btn-primary" @click="add">Add</button>
    <br/><br/>
    <ul class="list-group">
      <transition-group name="multiple">
        <li
          @click="remove(index)"
          style="cursor:pointer"
          class="list-group-item"
          v-for="(num, index) in numbers"
          :key="num"
        >
          {{ num }}
        </li>
      </transition-group>
    </ul>
  </div>

</template>

<script>
export default {
  data() {
    return {
      numbers: [1, 2, 3, 4, 5]
    };
  },
  methods: {
    add() {
      let pos = Math.floor(Math.random() * this.numbers.length);
      this.numbers.splice(pos, 0, this.numbers.length + 1);
    },
    remove(index) {
      this.numbers.splice(index, 1);
    }
  }
};
</script>

<style>
.multiple-enter {
  opacity: 0;
  transform: translateY(20px);
}

.multiple-enter-active {
  transition: all 0.5s;
}

.multiple-leave {
}

.multiple-leave-active {
  transition: all 0.3s;
  transform: translateY(20px);
  opacity: 0;
  position: absolute;
}

.multiple-move {
  transition: transform .5s;
}
</style>
