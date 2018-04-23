<template>
    <div id="app">
        <b-container fluid class="py-1">
          <b-row>
            <b-col cols="2"></b-col>
            <b-col cols="8">
            <b-form @submit.prevent="onSubmit">
                <b-form-group label="First Name"
                    label-for="firstName">
                    <b-form-input id="firstName"
                        type="text"
                        v-model="firstName"
                        placeholder="Enter FirstName">
                    </b-form-input>
                </b-form-group>
                <b-form-group label="Last Name"
                    label-for="lastName">
                    <b-form-input id="lastName"
                        type="text"
                        v-model="lastName"
                        placeholder="Enter LastName">
                    </b-form-input>
                </b-form-group>
                <b-form-group label="Age"
                    label-for="age">
                    <b-form-input id="age"
                        type="number"
                        v-model="age"
                        placeholder="Enter Age">
                    </b-form-input>
                </b-form-group>
                <b-button type="submit" variant="primary">Submit</b-button>
            </b-form>
              </b-col>
            <b-col cols="2"></b-col>
            </b-row>
            <br>
            <br>
            <UserTable :items="dataItems"></UserTable>
        </b-container>
    </div>
</template>

<script>
import UserTable from './components/UserTable'

export default {
  name: 'App',
  components: {
    UserTable
  },
  data () {
    return {
      firstName: '',
      lastName: '',
      age: '',
      dataItems: []
    }
  },
  methods: {
    onSubmit () {
      this.dataItems.push({ age: this.age, first_name: this.firstName, last_name: this.lastName })
      this.firstName = ''
      this.lastName = ''
      this.age = ''
    }
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
