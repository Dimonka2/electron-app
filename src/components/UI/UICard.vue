<template>
  <div
    v-bind:class="classCard"
  >
    <div class="px-2 py-2 border-b border-gray-200 flex justify-between items-center bg-white sm:py-4 sm:px-6 sm:items-baseline"
        v-if="hasHeader">
        <div class="flex-shrink min-w-0 flex items-center text-xl" v-if="hasTitle">
            <slot name="title"></slot>
        </div>
        <div class="flex flex-shrink-0 ml-4 items-center" v-if="hasTools">
            <slot name="tools"></slot>
        </div>
    </div>
    <div class="p-4 body" >
        <slot></slot>
    </div>
    <div class="px-4 py-3 bg-gray-200 sm:px-6" v-if="hasFooter">
        <slot name="footer"></slot>
    </div>
  </div>
</template>

<script>
    export const UiCard = {
        name: 'UiCard',
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
        computed: {
            hasBody(name = 'default') {
                return !!this.$slots[ name ] || !!this.$scopedSlots[ name ]
            },
            hasFooter() {
                return !!this.$slots.footer
            },
            hasHeader() {
                return !!this.$slots.title || !!this.$slots.tools
            },
            hasTitle() {
                return !!this.$slots.title
            },
            hasTools() {
                return !!this.$slots.tools
            },
            classCard() {
                let style = 'rounded border overflow-hidden'
                if (this.shadow) style += ' shadow-' + this.shadow
                return style
            }
        }
    };

    export default UiCard;
</script>