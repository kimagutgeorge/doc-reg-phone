<template>
<div class="nav-bar-wrapper position-absolute nav-item">
<div class="col-12 d-block">
    <div class="nav-bar-inner mt-2">
        <div class="d-block col-12 nav-bar bg-white mt-2">
            <router-link to="/home" class="row flex-no-wrap p-2 nav-item text-third" active-class="bg-third" @click="$emit('toggle_nav_bar')">
                <li class="col-10 ">
                    <!-- <router-link to="" class="text-third flex-no-wrap"> -->
                        <i class="fa-solid fa-home text-third"></i>
                        <span class="ms-2 custom-fw-bold">Dashboard</span>
                    <!-- </router-link> -->
                </li>
            </router-link>
            <!-- navbar item -->
                <router-link to="/documents" class="row flex-no-wrap p-2 nav-item text-third" active-class="bg-third" @click="$emit('toggle_nav_bar')">
                    <li class="col-10 ">
                        <!-- <router-link to="" class="text-third flex-no-wrap"> -->
                            <i class="fa-solid fa-home text-third"></i>
                            <span class="ms-2 custom-fw-bold">
                                Documents
                            </span>
                        <!-- </router-link> -->
                    </li>
                </router-link>

            <!-- navbar item -->
            <!-- <router-link to="/requests" class="row flex-no-wrap p-2 nav-item text-third" active-class="bg-third" @click="$emit('toggle_nav_bar')">
                <li class="col-10 ">
                        <i class="fa-solid fa-file-signature text-third"></i>
                        <span class="ms-2 custom-fw-bold">Requests</span>
                </li>
            </router-link> -->
            
            <!-- navbar item -->
            <div class="row flex-no-wrap p-2 nav-item text-third nav-drop-down"  @click="toggleDropDown('issuance')">
                <li class="col-10 ">
                    <router-link to="#" class="text-third flex-no-wrap" >
                        <i class="fa-solid fa-arrow-right-arrow-left text-third"></i>
                        <span class="ms-2 custom-fw-bold f-15">Collection & Returns</span>
                    </router-link>
                </li>
                <div class="col-2">
                    <i class="fa-solid text-third" :class="activeDropdown === 'issuance' ? 'fa-minus' : 'fa-plus'" ></i>
                </div>
            </div>
            <transition name="slide-fade">
                <div v-if="activeDropdown === 'issuance' " class="row flex-no-wrap p-2">

                    <router-link to="/issuance" class="row flex-no-wrap p-2 nav-item text-third" active-class="bg-third" @click="$emit('toggle_nav_bar')">
                        <li class="ms-4 mt-2 col-8">
                            <span class="custom-fw-lighter f-14">To Collect</span>
                        </li>
                    </router-link> 
                    <router-link to="/returns" class="row flex-no-wrap p-2 nav-item text-third" active-class="bg-third" @click="$emit('toggle_nav_bar')">
                        <li class="ms-4 mt-2 col-8">
                            <span class="custom-fw-lighter f-14">Returns</span>
                        </li>
                    </router-link>
                </div>
            </transition>
            <!-- navbar item -->
            <router-link to="/forms" class="row flex-no-wrap p-2 nav-item text-third" active-class="bg-third" @click="$emit('toggle_nav_bar')">
                <li class="col-10 ">
                    <!-- <router-link to="" class="text-third flex-no-wrap"> -->
                        <i class="fa-solid fa-list text-third"></i>
                        <span class="ms-2 custom-fw-bold">Forms</span>
                    <!-- </router-link> -->
                </li>
            </router-link>
            <!-- navbar item -->
            <div class="row flex-no-wrap p-2 nav-item text-third nav-drop-down" @click="toggleDropDown('reports')">
                <li class="col-10 ">
                    <router-link to="#" class="text-third flex-no-wrap">
                        <i class="fa-solid fa-chart-simple text-third"></i>
                        <span class="ms-2 custom-fw-bold">Reports</span>
                    </router-link>
                </li>
                <div class="col-2">
                    <i class="fa-solid text-third" :class="activeDropdown === 'reports' ? 'fa-minus' : 'fa-plus' "></i>
                </div>
            </div>
            <transition name="slide-fade">
                <div v-if="activeDropdown === 'reports' " class="row flex-no-wrap p-2">
                    <router-link to="/reports/issuance-returns" class="row flex-no-wrap p-2 nav-item text-third" active-class="bg-third" @click="$emit('toggle_nav_bar')">
                        <li class="ms-4 mt-2 col-8">
                            <span class="custom-fw-lighter f-14">Issuance & Return Logs</span>
                        </li>
                    </router-link>
                </div>
            </transition>
            <!-- navbar item -->
            <router-link to="/profile" class="row flex-no-wrap p-2 nav-item text-third" active-class="bg-third" @click="$emit('toggle_nav_bar')">
                <li class="col-10 ">
                        <i class="fa-solid fa-user text-third"></i>
                        <span class="ms-2 custom-fw-bold">Profile</span>
                </li>
            </router-link>
            <!-- navbar item -->
            <router-link to="#" class="row flex-no-wrap p-2 nav-item text-third" active-class="bg-third" @click="$emit('logout')">
                <li class="col-10 ">
                        <i class="fa-solid fa-power-off text-third"></i>
                        <span class="ms-2 custom-fw-bold">Logout</span>
                </li>
            </router-link>
            <!-- navbar item -->
        </div>
    </div>
</div>
</div>
</template>
<script>
export default {
    name: "NavBar",
    data(){
        return{
            activeDropdown: null,
        }
    },
    methods:{
        toggleDropDown(key){
            this.activeDropdown = this.activeDropdown === key ? null : key;
        }
        
    }
}
</script>