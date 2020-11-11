<template>
  <nav
    v-bind:class="classHeader"
  >
    <div class="flex items-center flex-shrink-0 text-white mr-6" >
        <slot name="logo"></slot>
    </div>
    <!-- menu -->
    <div class="block lg:hidden">
        <button class="flex items-center px-3 py-1 border rounded text-teal-200 border-teal-400 hover:text-white hover:border-white">
        <svg class="fill-current h-3 w-3" viewBox="0 0 20 20" xmlns="http://www.w3.org/2000/svg"><title>Menu</title><path d="M0 3h20v2H0V3zm0 6h20v2H0V9zm0 6h20v2H0v-2z"/></svg>
        </button>
    </div>
    <div class="w-full block flex-grow lg:flex lg:items-center lg:w-auto">
        <div class="text-sm lg:flex-grow">
            <a v-for="(alink, i) in alinks" :key="i"
                class="block mt-4 lg:inline-block lg:mt-0 text-teal-200 hover:text-white mr-4"
                :class="{ 'bg-teal-600': alink.isActive }"
                >
                    {{ alink.title }}

            </a>
        </div>
    </div>
    <div v-if="hasTools">
    </div>
  </nav>
</template>

<script>
    import DLinkVue from './DLink.vue'

    export const DHeader = {
        name: 'd-header',
        components: {
            alink: DLinkVue
        },
        props: {
            tag: {
                default: 'div',
                type: String,
            },
            color: {
                type: String,
                default: ''
            },
            shadow: String,
        },
        data() {
            return {alinks: [] }
        },
        mounted() {
            this.alinks = this.$children
            console.log(this, this.alinks)
        },
        computed: {
            hasTools() {
                return !!this.$slots.tools
            },
            classHeader() {
                let style = 'flex items-center justify-between flex-wrap bg-teal-500 p-6'
                if (this.shadow) style += ' shadow-' + this.shadow
                return style
            }
        }
    };

    export default DHeader;
</script>