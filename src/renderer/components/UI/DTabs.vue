<template>
  <div v-bind:class="classObject">
        <ul role="tablist" class="flex  border-b">
            <li v-for="(tab, i) in getTabs" :key="i"
                :aria-controls="tab.hash"
                :aria-selected="tab.isActive"
                class="mr-1"
                :class="{ '-mb-px': tab.isActive }"
                >
                <a href="#"
                    class="inline-block py-1 px-3 text-blue-500 hover:text-blue-800 font-semibold rounded-t whitespace-no-wrap"
                    :class="{
                        'bg-white border-l border-t border-r': tab.isActive,
                        'bg-gray-200': !tab.isActive
                        }"
                    @click="selectTab(tab)"
                >
                    <span>{{ tab.name }}</span>
                    <badge v-if="!!tab.badge">
                        {{ tab.badge }}
                    </badge>
                </a>
            </li>
        </ul>
        <div class="p-3">
            <slot></slot>
        </div>
  </div>
</template>

<script>
    import DBadgeVue from './DBadge.vue'
    import DTab from './DTab.vue'

    export default {
        name: 'd-tabs',
        components: {
            tab: DTab,
            badge: DBadgeVue
        },
        data() {
            return {tabs: [] }
        },
        mounted() {
            this.tabs = this.$children
            // console.log(this.tabs)
        },
        props: {
            cls: String
        },
        computed: {
            classObject: function () {
                let style = ''
                return style
            },
            getTabs: function () {
                let tabs = []
                this.tabs.forEach(tab => {
                    if(tab.$options._componentTag == 'tab') tabs.push(tab)
                })
                return tabs
            }
        },
        methods: {
            selectTab(selectedTab) {
                this.tabs.forEach(tab => {
                    tab.isActive = (tab.name == selectedTab.name)
                });
            }
        }

    }
</script>