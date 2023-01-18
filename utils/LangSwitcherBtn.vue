<script>
import Modal from "./Modal.vue";

export default {
  data() {
    return {
      isOpen: false
    }
  },
  components: {Modal},
}
</script>

<template>
  <div :class="$style.switcherBody" @click="isOpen = !isOpen">
    <img :class="$style.WorldIcon" src="../../assets/img/world-icon.svg" alt="language switching">
    <p :class="$style.SwitchTxt">English</p>
  </div>

  <Modal
      @changeOpenState="isOpen = !isOpen"
      v-if="isOpen"
      :isOpen="isOpen"
  >

  </Modal>

</template>

<style module lang="scss">
.switcherBody {
  cursor: pointer;
  transition: .3s linear;

  position: absolute;
  top: 0;
  right: 0;
  min-width: toRemMob(80);
  height: toRemMob(20);
  padding: toRemMob(2) toRemMob(5);

  margin-top: toRemMob(10);
  margin-right: toRemMob(10);

  display: flex;
  justify-content: space-between;
  align-items: center;

  &:hover {
    transition: .3s linear;
    border-radius: toRemMob(3);
    background-color: $color-opacity-white;
  }
}

.WorldIcon {
  width: toRemMob(15);
  height: toRemMob(15);
}

.SwitchTxt {
  @extend %notoSans-regular;
  color: $color-white;
  font-size: toRemMob(15);
}

.modalContainer {
  position: relative;
}
</style>