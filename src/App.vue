<script lang="ts">
    import Vue from 'vue';
    export default Vue.extend({
        mpType: 'app',
        onLaunch() {
            console.log('App Launch')
        },
        onShow() {
            console.log('App Show')
        },
        onHide() {
            console.log('App Hide')
        },
		onError(e) {
			console.log(e)
		}
    });
</script>

<style>
    /*每个页面公共css */
</style>
