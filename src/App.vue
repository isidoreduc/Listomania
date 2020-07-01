<template>
  <div id="app">
    <h4 class="bg-primary text-white text-center p-3">{{name}}'s Listomania</h4>
    <div class="container-fluid p-4">
      <div class="row">
        <div class="col font-weight-bold">Tasks</div>
        <div class="col-2 font-weight-bold">Done</div>
      </div>
      <div class="row" v-for = "t in tasks" v-bind:key="t.action">
        <div class="col">{{t.action}}</div>
        <div class="col-2">{{t.done}}</div>
      </div>
    </div>
  </div>
</template>

<script>
  export default {
    name: "App",
    data() {
      return {
        name : "Adrian",
        tasks : [
          {action: "Wet flowers", done: false},
          {action: "Eat breakfast", done: true},
          {action: "Sleep late", done: true},
          {action: "Work", done: false},
        ]
      }
    }
  };
</script>


