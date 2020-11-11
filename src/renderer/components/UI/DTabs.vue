<template>
  <div v-bind:class="classObject">
        <ul class="flex"> 
            <li v-for="tab in dtabs" v-bind:key="tab.name" 
                class="mr-3" :class="{ 'is-active': tab.isActive }">
                xx <a :href="tab.href" @click="selectTab(tab)">{{ tab.name }}</a>
            </li> 
        </ul>
        <div class="tabs-details">
            <slot></slot>
        </div>
  </div>
</template>

<script>
    import DTab from './DTab.vue'

    export default {
        name: 'd-tabs',
        components: {
            tab: DTab
        },
        data() {
            return {dtabs: [] }
        },
        created() {   
            let slot = this.$slots.default
            let self = this
            slot.forEach(function(entry) {
                    if(!!entry.tag) self.dtabs.push(entry)
                }
            )
            console.log(this, slot, this.dtabs)
        },
        props: {
            cls: String
        },
        computed: {
            classObject: function () {
                let style = ''
                return style
            }
        },
        methods: {
            selectTab(selectedTab) {
                this.dtabs.forEach(tab => {
                    tab.isActive = (tab.name == selectedTab.name)
                });
            }
        }

    }
</script>