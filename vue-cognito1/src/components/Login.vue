<template>
  <div class="login">
    <h2>ログイン</h2>
    <form @submit.prevent="login">
      <div>
        ユーザー名:
        <input type="text" placeholder="username" v-model="username" required>
      </div>
      <div>
        パスワード:
        <input type="password" placeholder="password" v-model="password" required>
      </div>
      <button>ログイン</button>
    </form>
    <router-link to="/confirm">確認コード入力</router-link>
    <router-link to="/singup">ユーザー登録</router-link>
    <div>
      status: {{ status }}
    </div>
  </div>
</template>

<script>
export default {
  name: 'Login',
  data () {
    return {
      username: '',
      password: '',
      status: ''
    }
  },
  methods: {
    login () {
      this.$cognito.login(this.username, this.password)
        .then(result => {
          this.$router.replace('/home')
        }, rejected => {
          console.log('reject..')
          this.status = 'IDかPWが間違ってます'
        })
        .then(err => {
          this.error = err
          console.log('err:' + JSON.stringify(this.error))
        })
    }
  }
}
</script>
