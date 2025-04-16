<template>
  <div class=" with-max-height">
      <div class="with-max-height-inner">
  <div class="row d-flex mx-2 no-margin">
      
      <PageTitle page_name="Profile"/>
  </div>
  <div class="card w-100 d-flex w-100 px-2 mt-2 no-border">
      <SubTitle title="Profile"/>
      <div class="w-100 d-flex flex-column">
        <div class="w-100 d-flex flex-row justify-content-center">
          <img src="/profiles/profile.png" class="profile-icon"/>
        </div>
        <div class="w-100 p-2 mt-2">
          <form @submit.prevent="" class="">
            <div class="form-group ">
              <label class="text-secondary">First Name</label>
              <input class="form-control" placeholder="First Name" required/>
            </div>
            <div class="form-group mt-4">
              <label class="text-secondary">Last Name</label>
              <input class="form-control" placeholder="Last Name" required/>
            </div>
            <div class="form-group mt-4">
              <label class="text-secondary">Email</label>
              <input type="email" class="form-control" placeholder="Email" required/>
            </div>
            <div class="form-group mt-4">
              <label class="text-secondary">Phone Number</label>
              <input type="number" class="form-control" placeholder="0700000000" required/>
            </div>
            <div class="form-group mt-4">
              <label class="text-secondary">Change Password</label>
              <div class="form-group d-flex flex-no-wrap form-control mt-2">
                <input :type="input_type" class="w-100 " placeholder="Password" required>
                <span class="btn bg-white login-btn" style="height:fit-content;" @click="viewPassword"><i class="fa-solid text-primary" :class="input_type === 'password' ? 'fa-eye' : 'fa-eye-slash' "></i></span>
                </div>
            </div>
            <button class="btn btn-primary mt-4 w-100">SAVE</button>
          </form>
         
        </div>
      </div>
      
  </div>
  </div>
  </div>
  </template>
  <script>
  // import ActionButton from '@/components/buttons/ActionButton.vue';
import PageTitle from '@/components/titles/PageTitle.vue';
import SubTitle from '@/components/titles/SubTitle.vue';
  export default{
      name: "UserProfile",
      components: { PageTitle, /* ActionButton,*/ SubTitle},
      data(){
        return{
          input_type: "password"
        }
      },
      methods: {
        viewPassword(){
          if(this.input_type === "password"){
                    this.input_type = "text"
                }else{
                    this.input_type = "password"
                }
        }
      }
      
  }
    
  </script>