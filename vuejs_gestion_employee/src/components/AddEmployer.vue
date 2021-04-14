<template>
  <div>
      <h1>{{ title }}</h1>
{{email}}
      <form class="card container p-4" style="text-align: left;">
      <div class="row">
        <div class="col-sm-6 mt-2">
        <label class="col-form-label col-form-label-lg">email<span class="text-danger">*</span></label>
          <input v-model="email" type="text" class="form-control" placeholder="email...">
        </div>
        <div class="col-sm-6 mt-2">
        <label class="col-form-label col-form-label-lg">employer<span class="text-danger">*</span></label>
          <input v-model="employer" type="text" class="form-control" placeholder="employer...">
        </div>
      </div>
      <div class="row">
        <div class="col-sm-6 mt-2">
        <label class="col-form-label col-form-label-lg">phone<span class="text-danger">*</span></label>
          <input v-model="phone" type="text" class="form-control" placeholder="phone">
        </div>
        <div class="col-sm-6 mt-2">
        <label class="col-form-label col-form-label-lg">CNSS<span class="text-danger">*</span></label>
          <input v-model="cnss" type="text" class="form-control" placeholder="cnss">
        </div>
      </div>
      <div class="row">
        <div class="col-sm-12 mt-2">
        <label class="col-form-label col-form-label-lg">adresse<span class="text-danger">*</span></label>
          <textarea v-model="address" type="text" class="form-control" placeholder="address..."></textarea>
        </div>
      </div>
      <input @click="saveEmployer()" type="button" value="Save" class="btn btn-dark mt-4 col-sm-3">
    </form>

  </div>
</template>

<script>
import axios from 'axios';
export default {
props: {
    title: String,
  },
  data(){
    return {
      email:'',
      employers:[]
    }
  },
  methods:{
    saveEmployer() {
    
      let newEmployer = {
        email     : this.email,
        employer  : this.employer,
        phone     : this.phone,
        cnss      : this.cnss,
        address   : this.address,

      }
      axios.post('http://localhost:3000/employers',newEmployer)
           .then(res => console.log(res.data))
    }
  }
}
</script>

<style>

</style>