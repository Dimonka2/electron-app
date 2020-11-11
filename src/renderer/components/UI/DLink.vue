<script>
    export default {
        props: {
            title: String,
            badge: String,
            route: String
        },
        data() {
            return {
                isActive: false
            };
        },
        computed: {
            classObject: function () {
                let style = ''
                return style
            }
        },
        mounted() {
            this.isActive = this.active;
        }
    }
</script>