<template>
    <div class="row col-12 d-flex mt-2 top-bar">
        <div class="flex-no-wrap nav-item" @click="$emit('toggle_nav_bar')" style="width: fit-content">
            <span class="fw-bold ms-2 f-20 text-primary" >SAFE</span>
            <i class="fa-solid fa-bars ms-2 nav-toggle f-20 text-primary"></i>
        </div>
    </div>
</template>
<script>
export default{
    name: "TopBar",
    data(){
        return{
            activeDropdown: null,
            activeUserDropdown: null
        }
    },
    methods: {
        toggleDropdown(){
            this.activeDropdown = !this.activeDropdown
        },
        toggleUserDropdown(){
            this.activeUserDropdown = !this.activeUserDropdown
        },
        logout(){
        this.$store.commit('setLoginState', true);
        this.$store.dispatch('login');
        }
    }
}
</script>
