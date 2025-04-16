<template>
    <div class=" with-max-height">
        <div class="with-max-height-inner">
    <div class="row d-flex mx-2 no-margin">
        
        <PageTitle page_name="Documents"/>
    </div>
    <div class="card w-100 d-flex w-100 px-2 mt-2 no-border">
        <SubTitle title="Returned Documents"/>
        <div class="w-100 d-flex flex-column scrollable-x">

          <table class="table">
            <thead>
              <!-- inventory report -->
              <tr>
                <th scope="col f-15">Name</th>
                <th scope="col f-15">
                  Type
                </th>
                <th scope="col f-15">Status</th>
                <th scope="col f-15">Date Returned</th>
              </tr>
             
            </thead>
            <tbody>
              <tr v-for="(doc, index) in documents" :key="index">
                <td class="f-14">{{ doc.name }}</td>
                <td class="f-14">{{ doc.type }}</td>
                <td class="f-14"><span class="status-check bg-success"> {{ doc.status }} </span></td>
                <td class="f-14">{{ doc.last_movement }}</td>
                
              </tr>
            </tbody>
            
          </table>

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
        name: "AllDocuments",
        components: { PageTitle, /* ActionButton, */ SubTitle},
        data(){
          return{
            documents: [
              { name: "2024/1",
              type: "Log book",
              status: "Returned",
              last_movement: "Apr 3" },
              { name: "2024/2",
              type: "Title Deed",
              status: "Returned",
              last_movement: "Apr 4" },
              { name: "2024/3",
              type: "Log book",
              status: "Returned",
              last_movement: "Apr 5" }
          ]
          }
        }
    }
      
    </script>