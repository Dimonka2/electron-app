<template>
  <div
    class="rounded overflow-hidden shadow-lg"
  >
    <div class="panel-header" v-if="hasHeader">
            <slot name="title"></slot>
    </div>
    <div class="p-4 body" >
        <slot></slot>
    </div>
    <div class="panel-footer" v-if="hasFooter">
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
        }
    };

    export default UiCard;
</script>