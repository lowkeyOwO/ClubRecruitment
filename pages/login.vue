<template>
  <div class="flex flex-col space-y-4 items-center justify-start">
    <div class="flex flex-col items-center justify-start space-y-2">
      <!-- replace this class with "box" -->
      <label for="username">Username:</label
      ><input
        type="text"
        id="username" v-model = "username"
        class="rounded-xl w-72 h-12 p-3 bg-gray-300"
        placeholder="Username"
      />
    </div>
    <div class="flex flex-col items-center justify-start space-y-2">
      <label for="password">Password:</label
      ><input
        type="password"
        id="password" v-model = "password"
        class="rounded-xl w-72 h-12 p-3 bg-gray-300"
        placeholder="Password"
      />
    </div>
    <button
      class="
        bg-gray-700
        p-3
        rounded-md
        text-white
        w-36
        transition
        duration-500
        ease-in-out
        hover:bg-gray-600
      "
      @click="LoginCheck"
    >
      Login
    </button>
  </div>
</template>

    <script>
import passwords from '@/data/passwords'
export default {
  data() {
    return {
      username: '',
      password: '',
      passwords,
    }
  },
  methods: {
    LoginCheck() {
        console.log(this.username)
      if (passwords.president_username_arr.includes(this.username)) {
        const ind = passwords.president_username_arr.indexOf(this.username)
        if (passwords.president_password_arr[ind] === this.password) {
          this.$router.push('/homepage')
        } else alert("username and password don't match")
      } else if (passwords.student_username_arr.includes(this.username)) {
        const ind = passwords.student_username_arr.indexOf(this.username)
        if (passwords.student_password_arr[ind] === this.password) {
          console.log('This is printed.')
        } else alert("username and password don't match")
      } else alert("account doesn't exist")
    },
  },
}
</script>
