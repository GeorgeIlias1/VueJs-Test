<template>
  <div>
    <header>User List</header>
    <div class="container">
      <div class="users">
        <active-user
        v-for="user in users"
        :key="user.id"
        :user-name="user.username"
        :age="user.age"/>
      </div>

      <user-data @add-user="addUser"/>
    </div>
  </div>
</template>

<script>
import ActiveUser from './components/ActiveUser.vue';
import UserData from './components/UserData.vue';
export default {
  components: { ActiveUser, UserData },
  data() {
    return {
      users: [
        {
          id: 1,
          username: 'sIREN_GR',
          age: 25 // integer test
        }
      ]
    };
  },
  methods: {
    addUser(name, age) {
      const newUserAdd = {
        username: name,
        age: +age //the + sign is converting the age from string to a number
      };
      this.users.push(newUserAdd);
    }
  }
};
</script>

<style lang="sass">
*
  box-sizing: border-box

html
  font-family: "Jost", sans-serif

body
  margin: 0

header
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.26)
  margin: 3rem auto
  border-radius: 10px
  padding: 1rem
  background-color: #58004d
  color: white
  text-align: center
  width: 90%
  max-width: 40rem

.container
  display: flex
  justify-content: space-evenly

.userForm
  display: inline !important

#app ul
  margin: 0
  padding: 0
  list-style: none

.users
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.26)
  border-radius: 10px
  height: auto
  padding: 1rem
  text-align: center
  width: 50%
  max-width: 30rem

#app li,
#app form
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.26)
  margin: 1rem auto
  border-radius: 10px
  padding: 1rem
  text-align: center
  width: 90%
  max-width: 40rem

#app h2
  font-size: 2rem
  border-bottom: 4px solid #ccc
  color: #58004d
  margin: 0 0 1rem 0

#app button
  font: inherit
  cursor: pointer
  border: 1px solid #ff0077
  background-color: #ff0077
  color: white
  padding: 0.05rem 1rem
  box-shadow: 1px 1px 2px rgba(0, 0, 0, 0.26)

#app button:hover,
#app button:active
  background-color: #ec3169
  border-color: #ec3169
  box-shadow: 1px 1px 4px rgba(0, 0, 0, 0.26)

#app input
  font: inherit
  padding: 0.15rem

#app label
  font-weight: bold
  margin-right: 1rem
  width: 7rem
  display: inline-block

#app form div
  margin: 1rem

</style>
