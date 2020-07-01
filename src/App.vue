<template>
  <div id="app">
    <h4 class="bg-primary text-white text-center p-3">{{name}}'s Listomania</h4>
    <div class="container-fluid p-4">
      <div class="row">
        <div class="col font-weight-bold">Tasks</div>
        <div class="col-2 font-weight-bold">Done</div>
      </div>
      <div class="row" v-for = "t in filteredTasks" v-bind:key="t.action">
        <div class="col">{{t.action}}</div>
        <div class="col-2">
          <input type="checkbox" v-model="t.done" class="form-check-input">
        </div>
      </div>
      <div class="row bg-secondary py-2 mt-2 text-white">
        <div class="col text-center">
          <input type="checkbox"  v-model="hideCompleted" class="form-check-input" />
          <label class="form-check-label font-weight-bold">Hide completed tasks</label>
        </div>
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
        ],
        hideCompleted : true  
      }
    },
    computed : {
      filteredTasks = () =>
        this.hideCompleted ? 
          this.tasks.filter(t => !t.done) : this.tasks 
    }
  };
</script>


