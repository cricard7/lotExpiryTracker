<template>
  <div class="about">

    <div class="container-fluid">
      <div class="row">
        <div class="col-md-12">
          <h1 class="text-center">Lot and Expiry Search</h1>
        </div>
      </div> 

      <div class="row">
        <div class="col-md-8">
          <div class="form-group mt-5">
            <h4>Paste Lot Excel Data WITH Headings:(id,product,manufacturer,lot,expiry)</h4>
            <textarea v-model="lots" class="form-control" id="exampleFormControlTextarea1" rows="3"></textarea>
          </div>

        </div>
      </div>
      
      <div class="row">
        <div class="col-md-6 offset-md-3">
          <input class="form-control form-control-lg mt-5 mb-5" type="text" placeholder="SEARCH LOT">
        </div>

      </div>


      <!-- List id,product,manufacturer,lot,expiry-->
      <div class="row">
        <div class="col-md-4">
          <h3>Matching Lots</h3>
            <div class="list-group">
                <div href="#" class="list-group-item list-group-item-action">
                  <h5 class="mb-1">LOT: </h5>
                  <h5 class="mb-1">EXPIRY: </h5>
                  <h5 class="mb-1">PRODUCT: </h5>
                  <h5 class="mb-1">Manufacturer: </h5>
                </div>  
          </div>

        </div>


        <div class="col-md-6"></div>
          <h3>ClipBoard</h3>
      </div>
      
      
    </div>
    


    <div class="jumbotron"> <h1>HI {{msg}}</h1> 
     


    </div>
  </div>
</template>

<script>
// @ is an alias to /src

var Papa = require('papaparse');
var Fuse = require('fuse.js');

export default {
  name: 'about',
  components: {
    
  },
  data: function(){
    return{
      msg: "msgdf",
      lots: "",
      loader: "",
      compounder: ""

    }

  },

  created: function(){
  },

  computed: {
    parsed: function(){

      var parsedobj = Papa.parse(this.lots, {header: true})
      console.log(parsedobj)
      return parsedobj
    }

  }
}
</script>
