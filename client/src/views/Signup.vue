<template>
    <div class="SignUp">
        <div class="Container-Signup">
             <form class="form" @submit.prevent="goto">
                <h2>Sign Up</h2>
                    <label>
                        <span>Name:</span>
                        <input type="text" required v-model="user.Name" />
                    </label>
                    <label>
                        <span>Email Address:</span>
                        <input type="email" required v-model="user.Email"/>
                    </label>
                    <label>
                        <span>Password:</span>
                        <input type="password" required v-model="user.Password"  />
                    </label>
                    <label>
                        <span>Confirm Password:</span>
                        <input type="password"  required v-model="user.Cpassword"/>
                    </label>
                    <button class="submit" type="submit">Sign Up</button>
                    <p class="question">Already a member?</p>
                    <router-link to="/login">Login</router-link>
            </form>
        </div>   
    </div>
</template>

<script>
export default {
    data(){
        return{
            user:{Name: null,
                Email: null,
                Password: null,
                Cpassword: null}
        }
    },
    methods:{
        goto(){
          this.$router.push('/create')
      }
    }

}
</script>

<style lang="scss" scoped>
.SignUp {
  width: 100%;
  height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  background: -webkit-linear-gradient(25rad, #000D3A, black);
  font-family: Poppins, sans-serif;
}
.Container-Signup {
  overflow: hidden;
  position: relative;
  width: 560px;
  height: 600px;
  background: #fff;
  box-shadow: 0 19px 38px rgba(0, 0, 0, 0.3), 0 15px 12px rgba(0, 0, 0, 0.22);
}
.form input,
button {
  border: none;
  outline: none;
  background: none;
}
.form {
  position: relative;
  height: 100%;
  padding: 30px 30px;
}
.form h2 {
  width: 100%;
  font-size: 30px;
  text-align: center;
}

.form label {
  display: block;
  width: 260px;
  margin: 25px auto 0;
  text-align: center;
}

.form label span {
  font-size: 14px;
  font-weight: 600;
  color: #505f75;
  text-transform: uppercase;
}

.form input {
  display: block;
  width: 100%;
  margin-top: 5px;
  font-size: 16px;
  padding-bottom: 5px;
  border-bottom: 1px solid rgba(109, 93, 93, 0.4);
  text-align: center;
  font-family: Poppins, sans-serif;
}

.form button {
  display: block;
  margin: 30px auto 0px auto;
  width: 260px;
  height: 36px;
  border-radius: 30px;
  color: #fff;
  font-size: 15px;
  cursor: pointer;
}

.submit {
  text-transform: uppercase;
  font-weight: 600;
  font-family: Poppins, sans-serif;
  background: -webkit-linear-gradient(left, #000D3A, black);
}

.submit:hover {
  background: -webkit-linear-gradient(left, black, #000D3A);
}

.question {
    
  margin-top: 20px;
  margin-bottom: -10px;
  margin-left: 10px;
  text-align: center;
  font-size: 14px;
  font-weight: 600;
  color: #0c0101;
}
.form a {
  text-decoration: none;
  text-align: center;
  font-size: 15px;
  font-weight: 600;
  color: #0c0101;
  cursor: pointer;
  position: relative;
  top: 15px;
  left: 46%;
}
@media (max-width: 600px) {
  .Container-Login{
    width: 80vw;
  }
  .form label,
  .form button {
    width: 80%;
  }
}
</style>