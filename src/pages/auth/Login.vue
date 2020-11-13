<template>
<q-card v-bind:style="$q.screen.lt.sm?{'width': '80%'}:{'width':'30%'}">
    <q-card-section>
        <q-avatar size="103px" class="absolute-center shadow-10">
            <q-icon name="person" color="primary" />
        </q-avatar>
    </q-card-section>
    <q-card-section>
        <div class="text-center q-pt-lg">
            <div class="col text-h6 ellipsis">
                Log in
            </div>
        </div>
    </q-card-section>
    <q-card-section>
        <q-form class="q-gutter-md">
            <q-input filled v-model="username" label="Username" lazy-rules />

            <q-input type="password" filled v-model="password" label="Password" lazy-rules />

            <div>
                <q-btn label="Login" to="/" type="button" color="primary" />
                <q-btn label="Forgot password" to="/" type="button" color="secondary" class="q-ml-md" />
            </div>
        </q-form>
    </q-card-section>
</q-card>
</template>

<script>
export default {
    data() {
        return {
            username: 'Pratik',
            password: '12345',
            short: "DG"
        }
    },
}
</script>

<style>
.bg-image {
    background-image: linear-gradient(135deg, #7028e4 0%, #e5b2ca 100%);
}
</style>
