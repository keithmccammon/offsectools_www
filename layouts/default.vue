<template>
    <div class="container-fluid vh-100 p-0 m-0">
        <div class="row vh-100 p-0 m-0">
            <Tagbar ref="tagbar"></Tagbar>
            <div id="main" class="col p-0 m-0">
                <Topbar></Topbar>
                <div class="row p-0 m-0">
                    <div class="col p-0 m-0">
                        <MainContent></MainContent>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>


<script>
import Topbar from '~/components/Topbar.vue';
import Tagbar from '~/components/Tagbar.vue';
import MainContent from '~/components/MainContent.vue';

export default {
    name: 'default_layout',
    components: {
        Topbar, Tagbar, MainContent
    },
    async mounted() {
        this.$store.dispatch( 'getTags' );
        this.$store.dispatch( 'getTools' );
        this.$store.dispatch( 'getContributors' );
        this.$store.dispatch( 'getCategories' );
    },
}
</script>

<style scoped>
</style>
