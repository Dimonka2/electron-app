<template>
  <span v-bind:class="classObject">
    <slot></slot>
  </span>
</template>

<script>
  export default {
    name: 'd-badge',
    computed: {
      classObject: function () {
        let style = 'inline-block px-2 font-semibold tracking-wide'
        if (this.fontColor) style += ' text-' + this.fontColor
        if (this.rounded) style += ' rounded-' + this.rounded
        if (this.color) style += ' bg-' + this.color
        if (this.size) style += ' text-' + this.size
        if (this.cls) style += ' ' + this.cls
        return style
      }
    },
    props: {
      cls: String,
      color: {
        type: String,
        default: 'blue-500'
      },
      fontColor: String,
      rounded: {
        type: String,
        default: 'full'
      },
      size: {
        type: String,
        default: 'xs'
      }

    }
  }
</script>