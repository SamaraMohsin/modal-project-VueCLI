<template>
    <div class="backdrop" @click.self="closeModal">
      <div class="modal" :class="{sale: theme ==='sale'}">
        <!-- <h1>{{ header }}</h1>
        <h2>{{ header2 }}</h2>
        <p>{{ text }}</p> -->
        <slot>defualt content</slot>
        <div class="actions">
          <slot name="links"></slot>
        </div>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    //props: ['header', 'text','theme','header2'], //parent to child, hum send kr rahe app.vue se aur accept yahan kr rahe hain, its not necessary k jo hum yahan accept kr rahe hain wo parent me ho bhi error nhi aayega
    props: ['theme'], //parent to child, hum send kr rahe app.vue se aur accept yahan kr rahe hain, its not necessary k jo hum yahan accept kr rahe hain wo parent me ho bhi error nhi aayega
    
    methods: {
      closeModal(){
          this.$emit('close')
      }
    }
  }
</script>
  <style >
    .modal {
      width: 400px;
      padding: 20px;
      margin: 100px auto;
      background: white;
      border-radius: 10px;
    }
    .backdrop {
      top: 0;
      position: fixed;
      background: rgba(0,0,0,0.5);
      width: 100%;
      height: 100%;
    }
    .modal h1{
        color: aqua;
        border: none;
        padding: 0;
    }
    .modal p{
        font-style: normal;
    }
    .modal.sale{
      background: crimson;
      color: white;
    }
    .modal.sale h1{
      color: white;
    }
    .modal .actions {
    text-align: center;
    margin: 30px 0 10px 0;
    /* color: #333; */
  }
  .modal .actions a {
    color: #333;
    padding: 8px;
    border: 1px solid #eee;
    border-radius: 4px;
    text-decoration: none;
    margin: 10px;
  }
  .modal.sale .actions {
    color: white;
  }
  .modal.sale .actions a {
    color: white;
  }

  </style>