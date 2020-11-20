<template>
  <div>
    <ejs-listview
      id="List"
      :dataSource="data"
      headerTitle="Contacts"
      showHeader="true"
      cssClass="e-list-template"
      :template="template"
      sortOrder="Ascending"
      width="350px"
    ></ejs-listview>
  </div>
</template>

<script>
import Vue from "vue";
import { ListViewPlugin } from "@syncfusion/ej2-vue-lists";
import { ButtonPlugin } from "@syncfusion/ej2-vue-buttons";

Vue.use(ListViewPlugin);
Vue.use(ButtonPlugin);

var demoVue = Vue.component("demo", {
  template: `<div class="e-list-wrapper e-list-multi-line">    
      <ejs-button v-on:click.native='btnClick'>{{data.ShipCountry}}</ejs-button>
    </div>`,
  data() {
    return {
      data: {},
    };
  },
  methods: {
    btnClick: function (event) {
      var listObj = document.getElementById("List").ej2_instances[0];
      var btnText = event.target.textContent;
      for (var i = 0; i < listObj.dataSource.length; i++) {
        if (btnText === listObj.dataSource[i].ShipCountry) {
          console.log(listObj.dataSource[i]);
          console.log("index :" + i);
        }
      }
    },
  },
});
var empData = [
  {
    OrderID: 10248,
    ShipCountry: "France",
    CustomerName: "Paul Henriot",
  },
  {
    OrderID: 10249,
    ShipCountry: "Germany",
    CustomerName: "Karin Josephs",
  },
  {
    OrderID: 10250,
    ShipCountry: "Brazil",
    CustomerName: "Mario Pontes",
  },
  {
    OrderID: 10251,
    ShipCountry: "France",
    CustomerName: "Mary Saveley",
  },
];

export default Vue.extend({
  data: function () {
    return {
      data: empData,
      fields: { text: "text" },
      template: function () {
        return { template: demoVue };
      },
    };
  },
  mounted: function () {
    //EventBus.$on("getData", this.getData);
  },
  methods: {},
});
</script>

<style>
</style>