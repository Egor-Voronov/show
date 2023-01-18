<script>
export default {
  data() {
    return {
      overflowFromScript: isOpen ? 'hidden' : 'auto'
    }
  },
  props: {
    isOpen: Boolean
  }
  ,
  methods: {
    changeOpenState() {
      this.$emit('changeOpenState')
    }
  }
}

</script>

<template>
  <teleport to="body">
    <div :class="$style.modal" @click.self="changeOpenState()">
      <div :class="$style.modalBody">
        <button :class="$style.modalClose" @click.self="changeOpenState()">
          <img alt="close language changing modal" src="../../assets/img/x-mark.svg" @click.self="changeOpenState()">
        </button>
        <h2>dff</h2>
      </div>

    </div>
  </teleport>
</template>

<style lang="scss" module>
.modal {
  position: fixed;
  top: 0;
  left: 0;
  background-color: $color-modal-area;
  width: 100%;
  height: 100%;
  overflow: hidden;

  display: flex;
  justify-content: center;
  align-items: center;
  z-index: 999;

  &Body {
    background-color: $color-white;
    padding: toRemMob(50);
    border-right: toRemMob(10);
    position: relative;
  }

  &Close {
    position: absolute;
    cursor: pointer;
    top: 0;
    right: toRemMob(-1);

    background-color: rgba(#fff, 0);
    border: none;

    img {
      width: toRemMob(12);
      height: toRemMob(12);
    }
  }

  body {
    overflow: v-bind(overflowFromScript);
  }
}
</style>