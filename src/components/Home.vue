<template>
    <div class="test">
        <input type="text" v-model="title">
        <h4>{{title}}</h4>
        <span v-html="titleHtml"></span> from
        <p v-if="showName">{{user.firstName}} <span v-text="user.lastName"></span></p>
        <p v-else="showName">Nobody</p>
        <ul>
            <li v-for="item in items">{{item.title}}</li>
        </ul>

        <input type="text" v-on:keyup="pressKey" />
        <button v-on:click="enterHit">Submit</button>
        <br/>
        <span v-if="textSubmitted">This value was entered {{textSubmitted}}</span>
    </div>
</template>

<script>
  export default {
    name: 'home',
    data () {
      return {
        title: 'Hello World',
        titleHtml: '<h3>Hello Again</h3>',
        textSubmitted: '',
        user: {
          firstName: 'John',
          lastName: 'Doe'
        },
        showName: true,
        items: [{
          title: 'item 1'
        }, {
          title: 'item 2'
        }, {
          title: 'item 3'
        }]
      }
    },
    methods: {
      greet: function (name) {
        window.alert(name)
      },
      pressKey (e) {
        this.title = e.target.value
      },
      enterHit () {
        this.textSubmitted = this.title
      }
    }
  }
  </script>


<style scoped>

</style>