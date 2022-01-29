<template>
  <div class="flex flex-col space-y-4 items-center justify-start">
    <span>SVCE CLUBS</span>
    <style>
      span {
        position: absolute;
        left: 50%;
        top: 15%;
        font-family: fantasy;
        transform: translate(-50%, -50%);
        display: block;
        color: #cf1b1b;
        font-size: 124px;
        letter-spacing: 8px;
      }

      span::after {
        content: 'SVCE CLUBS';
        position: absolute;
        color: transparent;
        background-image: repeating-linear-gradient(
          135deg,
          transparent 0,
          transparent 2px,
          white 2px,
          white 4px
        );
        -webkit-background-clip: text;
        top: 0px;
        left: 0px;
        transition: 1s;
      }
    </style>
    <div class="box transition duration-500 ease-in-out">
      <input type="text" name="" placeholder="Username" v-model="username" />
      <input
        type="password"
        name=""
        placeholder="Password"
        v-model="password"
      />

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
  </div>
</template>

    <script>
import passwords from '@/data/passwords'
export default {
  data() {
    return {
      username: '',
      password: '',
    }
  },
  methods: {
    LoginCheck() {
      if (passwords.president_username_arr.includes(this.username)) {
        let ind = passwords.president_username_arr.indexOf(this.username)
        if (passwords.president_password_arr[ind] === this.password) {
          this.$router.push('/presidenthomepage')
        } else alert("username and password don't match")
      } else if (passwords.student_username_arr.includes(this.username)) {
        let ind = passwords.student_username_arr.indexOf(this.username)
        if (passwords.student_password_arr[ind] === this.password) {
          this.$router.push('/studenthomepage')
        } else alert("username and password don't match")
      } else alert("account doesn't exist")
    },
  },
}
</script>

