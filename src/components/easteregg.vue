<template>
  <div class="easteregg" :class="{ 'visible': visible }">
    <slot></slot>
  </div>
</template>

<script>
  export default {
    name: 'easteregg',
    props: [ 'eggs', 'duration' ],
    data () {
      return {
        buffer: [],
        timer: null,
        visible: false
      }
    },
    eggs: [
      ['ArrowUp', 'ArrowUp', 'ArrowDown', 'ArrowDown', 'ArrowLeft', 'ArrowRight', 'ArrowLeft', 'ArrowRight', 'b', 'a'],
      ['ArrowUp', 'ArrowUp', 'ArrowDown', 'ArrowDown', 'ArrowLeft', 'ArrowRight', 'ArrowLeft', 'ArrowRight', 'B', 'A'],
      ['8', '8', '2', '2', '4', '6', '4', '6', 'b', 'a'],
      ['8', '8', '2', '2', '4', '6', '4', '6', 'B', 'A'],
      'easter'
    ],
    methods: {
      resetBuffer() {
        if (this.timer) {
          clearTimeout(this.timer);
        }
        this.buffer = [];
      },
      resetEasterEgg() {
        if (this.timer) {
          clearTimeout(this.timer);
        }
        this.buffer = [];
        this.visible = false;
      }
    },
    mounted() {
      document.addEventListener('keyup', (e) => {
        if (this.timer) clearTimeout(this.timer);
        this.buffer.push(e.key);
        const eggs = this.eggs ? this.eggs : this.$options.eggs;
        for (let egg of eggs) {
          if (sameArray(this.buffer, egg)) {
            this.$emit('easter', egg);
            this.visible = true;
            this.buffer = [];
            if (this.duration) {
              setTimeout(this.resetEasterEgg, this.duration);
            }
            return;
          }
        }
        this.timer = setTimeout(this.resetBuffer, 1000);
      })
    }
  }

  const sameArray = (a, b) => {
    if (a.length !== b.length) {
      return false;
    }
    for (var i = 0, l = a.length; i < l; i++) {
      if (a[i] !== b[i]) {
        return false;
      }
    }
    return true;
  }
</script>

<style lang="scss">
  .easteregg {
    display: none;
    position: absolute;
    top: 50%;
    left: 50%;
    z-index: 10;
    transform: translate(-50%, -50%);
    width: 100%;
    height: 100%;
    text-align: center;
    background-color: white;

    img {
      max-height: 100%;
      max-width: 100%;
    }
  }
  .easteregg.visible {
    display: block;
  }
</style>