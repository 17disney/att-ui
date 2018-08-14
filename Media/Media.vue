<style lang='stylus'>
@require '../../../styles/disney/var/color.styl';

.att-media {
  border-radius: 100%;
  overflow: hidden;
  position: relative;

  &__icon {
    position: absolute;
    left: 0px;
    top: 0px;
    right: 0px;
    bottom: 0px;
    background: $color-primary;
    text-align: center;
    color: #FFF;
    line-height: 1;
    z-index: 1;
  }

  &__img {
    z-index: 2;
    position: relative;
  }

  &--finderListMobileSquare {
    &.size-large {
      width: 65px;
      height: 65px;

      .att-media__icon {
        font-size: 28px;
        line-height: 65px;
      }
    }

    &.size-medium {
      width: 56px;
      height: 56px;

      .att-media__icon {
        font-size: 23px;
        line-height: 56px;
      }
    }

    &.size-small {
      width: 48px;
      height: 48px;

      .att-media__icon {
        line-height: 48px;
      }
    }

    &.size-mini {
      width: 28px;
      height: 28px;

      .att-media__icon {
        line-height: 28px;
      }
    }
  }

  &--finderDetailMobileHero {
    max-width: 600px;
  }

  >img {
    width: 100%;
    height: 100%;
  }
}
</style>
<template>
  <div class="att-media" :class="['att-media--' + type, 'size-' + size]">
    <img class="att-media__img" :src="url" alt="">
    <att-icon class="att-media__icon" name="attractions"></att-icon>
  </div>
</template>

<script>
export default {
  name: 'att-media',

  components: {},

  props: {
    medias: {
      type: Array
    },
    type: {
      type: String,
      default: 'finderListMobileSquare'
    },
    size: {
      type: String,
      default: 'medium'
    }
  },

  data() {
    return {
    }
  },

  computed: {
    url() {
      return this.medias.find(_ => _.type === this.type)['url']
    }
  },

  mounted() {

  },

  methods: {}
}
</script>
