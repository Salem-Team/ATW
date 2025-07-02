<template>
  <div class="login">
    <div class="container">
      <form @submit.prevent="Submit">
        <div class="title">Welcome back</div>
        <p>Sign in to access your NFT marketplace.</p>
        <div class="inputs">
          <input
            v-model="email"
            type="email"
            placeholder="Enter your email..."
          />
          <input v-model="password" type="password" placeholder="Password" />
        </div>
        <div class="options">
          <div class="remember_me">
            <input type="checkbox" key="remember_me" id="remember_me" />
            <label for="remember_me">Remember me</label>
          </div>
          <div class="forget_password">Forgot your password?</div>
        </div>
        <div class="error" v-if="error">
          <font-awesome-icon :icon="['fas', 'circle-exclamation']" />
          <div>
            {{ error }}
          </div>
        </div>
        <span v-if="isLoading">Loading...</span>
        <button
          class="submit"
          :disabled="isLoading || !email.trim() || !password.trim()"
        >
          <span v-if="isLoading">Loading...</span>
          <span v-else>Sign in</span>
        </button>

        <div class="sign_up">
          Don't have an account? <router-link to="/">Sign up</router-link>
        </div>
      </form>
      <footer>© 2023 VMeta 3. All rights reserved.</footer>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      email: "",
      password: "",
      error: "",
      Show_error: null,
      isLoading: false,
    };
  },
  methods: {
    async Submit() {
      if (this.email.trim() === "") {
        this.error = "The email field is required.";
        return;
      }
      if (this.password.trim() === "") {
        this.error = "The password field is required.";
        return;
      }

      try {
        this.isLoading = true;
        this.error = "";
        const res = await fetch(
          "http://atwltd-001-site1.qtempurl.com/api/login",
          {
            method: "POST",
            headers: {
              "Content-Type": "application/json",
            },
            body: JSON.stringify({
              email: this.email,
              password: this.password,
            }),
          }
        );
        const data = await res.json();
        console.log("data", data);
        if (data.status === 200 && data.data.token) {
          localStorage.setItem("token", data.data.token);
          localStorage.setItem("user", JSON.stringify(data.data));
          this.$router.push("/");
          window.dispatchEvent(new Event("loginStatusChanged"));
        } else {
          this.error = "The email or password you entered is incorrect.";
        }
      } catch (err) {
        console.log("err", err);
        this.error = "An error occurred. Please try again.";
      } finally {
        this.isLoading = false;
      }
    },
  },
};
</script>

<style lang="scss" scoped>
.login {
  background: linear-gradient(to bottom, #291b3f, transparent), #120f1d;
  height: 100vh;
  overflow: hidden;
  .container {
    display: flex;
    align-items: center;
    justify-content: center;
    flex-direction: column;
    position: relative;
    width: 100%;
    height: 100%;
    form {
      background: #9a9a9a33;
      padding: 20px;
      border-radius: 16px;
      color: #fff;
      width: 448px;
      min-height: 458px;

      .title {
        margin-top: 30px;

        font-size: 32px;
        text-align: center;
        font-weight: bold;
      }
      p {
        color: #9ca3af;
        text-align: center;
      }
      .inputs {
        margin-top: 30px;
        display: flex;
        flex-direction: column;
        width: 100%;

        border-radius: 6px;
        background: #9a9a9a33;
        input {
          padding: 10px;
          border: 1px solid #6e6c6c;

          &:first-child {
            border-top-right-radius: 5px;
            border-top-left-radius: 5px;
          }
          &:last-child {
            border-bottom-left-radius: 5px;
            border-bottom-right-radius: 5px;
          }
        }
      }
      .options {
        display: flex;
        align-items: center;
        justify-content: space-between;
        margin-top: 30px;
        .remember_me {
          display: flex;
          align-items: center;

          gap: 10px;
          color: #d1d5db;
          input {
            width: 16px;
            height: 16px;
            border-radius: 2.5px;
            border-width: 1px;
            border: 1px solid #767676;
            background: #ffffff80;
          }
          label {
            cursor: pointer;
            color: #d1d5db;
            transition: 0.3s;

            &:hover {
              filter: saturate(1.5);
            }
          }
        }
        .forget_password {
          cursor: pointer;
          color: #c084fc;
          transition: 0.3s;

          &:hover {
            filter: saturate(1.5);
          }
        }
      }
      .submit {
        background: #5a486a;
        margin-top: 30px;
        width: 100%;
        padding: 10px;
        border-radius: 5px;
        cursor: pointer;
        transition: 0.3s;
        &:hover {
          filter: saturate(1.5);
        }
      }
      button.submit[disabled] {
        opacity: 0.6;
        cursor: not-allowed;
      }

      .sign_up {
        text-align: center;
        margin: 30px 0 10px;
        color: #9ca3af;
        a {
          color: #c084fc;
        }
      }
    }
    .error {
      color: red;
      margin: 10px 0 0;
      text-align: center;
      display: flex;
      justify-content: center;
      align-items: center;
      gap: 10px;
    }
    footer {
      width: 100%;
      position: absolute;
      bottom: 10px;
      left: 50%;
      transform: translate(-50%);
      color: #9ca3af;
      font-size: 14px;
      text-align: center;
    }
  }
}

@media (max-width: 720px) {
  form {
    width: 90% !important;
  }
}

@keyframes fadeUp {
  0% {
    opacity: 0;
    transform: translateY(30px);
  }
  100% {
    opacity: 1;
    transform: translateY(0);
  }
}

// Animation

form .title,
form p,
form .inputs,
form .options,
form .submit,
form .sign_up {
  opacity: 0;
  animation: fadeUp 1s ease-out forwards;
}

form .title {
  animation-delay: 0.3s;
}
form p {
  animation-delay: 0.6s;
}
form .inputs {
  animation-delay: 0.9s;
}
form .options {
  animation-delay: 1.2s;
}
form .submit {
  animation-delay: 1.5s;
}
form .sign_up {
  animation-delay: 1.8s;
}
</style>
