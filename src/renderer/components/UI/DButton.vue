<template>
  <button v-bind:class="classObject"
    @click="$router.push(route)">
    <slot></slot>
  </button>
</template>

<script>
  export default {
    name: 'd-button',
    computed: {
      classObject: function () {
        let style = 'rounded'
        let sizeList = {
          xs: 'text-xs py-1 px-2',
          sm: 'text-sm py-2 px-3',
          md: 'text-md py-2 px-4',
          xl: 'text-xl py-3 px-5',
          xxl: 'text-2xl py-4 px-6'
        }
        if (sizeList[this.size]) style += ' ' + sizeList[this.size]
        let colorList = ['primary', 'secondary', 'success', 'danger']
        if (colorList.indexOf(this.color) !== -1) {
          let colorList = {
            primary: 'text-white active:bg-indigo-600 bg-indigo-600 hover:bg-indigo-500',
            secondary: 'text-gray-700 border hover:bg-gray-100 hover:text-gray-500 focus:outline-none focus:border-blue-300 focus:shadow-outline-blue active:bg-gray-50 active:text-gray-800 border-gray-300',
            success: 'text-white bg-green-500 hover:bg-green-400 focus:outline-none focus:border-green-700 focus:shadow-outline-green',
            danger: 'text-white bg-red-600 hover:bg-red-500 focus:outline-none focus:border-red-700 focus:shadow-outline-red'
          }
          style += ' ' + colorList[this.color]
        } else {
          style += ' text-white bg-' + this.color + '-500 hover:bg-' + this.color + '-700 ' + this.cls
        }
        return style + ' ' + this.cls
      }
    },
    props: {
      cls: String,
      color: {
        type: String,
        default: 'primary'
      },
      route: String,
      size: {
        type: String,
        default: 'md'
      }
    }
  }
</script>