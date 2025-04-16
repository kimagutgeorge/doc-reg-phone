<template>
    <div class=" with-max-height">
        <div class="with-max-height-inner">
    <div class="row d-flex mx-2 no-margin">
        
        <PageTitle page_name="Documents"/>
    </div>
    <div class="card w-100 d-flex w-100 px-2 mt-2 no-border">
        <SubTitle title="All Documents"/>
        <div class="w-100 d-flex flex-column">
          <div v-for="(doc, index) in documents" :key="index" class="card w-100 p-2 mt-2">
            <p ><span class="text-secondary custom-fw-bold">Name: </span><span>{{ doc.name }}</span></p>
            <p ><span class="text-secondary custom-fw-bold">Type: </span><span>{{ doc.type }}</span></p>
            <p ><span class="text-secondary custom-fw-bold">Status: </span><span><i class="fa-solid fa-check status-check bg-primary text-white"></i></span></p>
            <p ><span class="text-secondary custom-fw-bold">Last Movement: </span><span>{{ doc.last_movement }}</span></p>
            <ActionButton 
                  :dropdown_actions="{
                    view: {
                      action: () => viewItem(itemId),
                      iconClass: 'text-primary'
                    },
                    return: {
                      action: () => editItem(itemId),
                      iconClass: 'text-primary'
                    },
                  }"
                />
          </div>
        </div>
        
    </div>
    </div>
    </div>
    </template>
    <script>
    import ActionButton from '@/components/buttons/ActionButton.vue';
import PageTitle from '@/components/titles/PageTitle.vue';
import SubTitle from '@/components/titles/SubTitle.vue';
    export default{
        name: "AllDocuments",
        components: { PageTitle, ActionButton,SubTitle},
        data(){
          return{
            documents: [
              { name: "2024/1",
              type: "Log book",
              last_movement: "Apr 3" },
              { name: "2024/2",
              type: "Title Deed",
              last_movement: "Apr 4" },
              { name: "2024/3",
              type: "Log book",
              last_movement: "Apr 5" }
          ]
          }
        }
    }
      
    </script>