<template>
  
  <video autoplay loop muted plays-inline class="back-video">
    <source src="../assets/back-ground-vid2.mp4">
  </video>

  <nav>
    <a @click="aboutToggle">About</a>
    <a @click="mainToggle">Skate-Rate</a>
    <a @click="signInUpToggle">Sign in/up</a>
  </nav>


  <div class="Main" v-if="main">
    
  </div>

  <div class="About" v-if="about">
    <h1>About me</h1>
    <p class="paragraphAbout">It seemed like it should have been so simple. There was nothing inherently difficult with getting the project done. It was simple and straightforward enough that even a child should have been able to complete it on time, but that wasn't the case. The deadline had arrived and the project remained unfinished.</p>
  </div>

  <div class="SignIn" v-if="signInUp">
    <div v-if="switchSignIn" class="SignIn">
      <h1>Sign In</h1>
      <input class="SignInInput" type="text" placeholder="Email" />
      <input class="SignInInput" type="text" placeholder="Passwort" />
      <button class="sign">Sign In</button>
      <p>Don't have an Account?</p>
      <button class="sign" @click="switchSignInUp">Sign Up here!</button>
    </div>
    <div v-if="switchSignUp" class="SignIn">
      <h1>Sign Up</h1>
      <input class="SignInInput" type="text" placeholder="Email" />
      <input class="SignInInput" type="text" placeholder="Passwort" />
      <button class="sign">Sign Up</button>
      <p>Already have an Account?</p>
      <button class="sign" @click="switchSignInUp">Sign In here!</button>
    </div>
  </div>

<div class="bottomList">
  <div class="footer">
  <p>Danke für eure Unterstützung</p>
  </div>
</div>
</template>

<script>
export default {
  data() {
    return {
      main: true,
      about: false,
      signInUp: false,
      switchSignIn: true,
      switchSignUp: false
    };
  },

  methods: {
    mainToggle() {
      this.about = false;
      this.signInUp = false;
      if (this.main == true) {
        this.main = true;
      } else {
        this.main = !this.main;
      }
    },

    aboutToggle() {
      this.main = false;
      this.signInUp = false;
      if (this.about == false) {
        this.about = !this.about;
      } else {
        this.about = true;
      }
    },

    signInUpToggle() {
      this.main = false;
      this.about = false;
      if (this.signInUp == false) {
        this.signInUp = !this.signInUp;
      } else {
        this.signInUp = true;
      }
    },

    switchSignInUp() {
      this.switchSignIn = !this.switchSignIn
      this.switchSignUp = !this.switchSignUp
    }
  },
};
</script>

<style scoped>
/* ----------------------------------------------------------------------- */
/* NavBar */
/* ----------------------------------------------------------------------- */
body {
  font-family: monospace;
}

nav {
  display: flex;
  height: 80px;
  background-color: white;
  box-shadow: 0 0 20px rgba(0, 0, 0, 0.5);
}

nav a:nth-child(1) {
  flex: 1;
  font-size: 1.6rem;
}

nav a:nth-child(2) {
  border-left: 0.1px solid black;
  border-right: 0.1px solid black;
}

nav a:nth-child(3) {
  flex: 1;
  font-size: 1.6rem;
}

nav a {
  flex: 2;
  display: flex;
  justify-content: center;
  align-items: center;
  font-size: 2rem;
  color: black;
  transition: all 0.3s;
  font-weight: bold;
  font-family: monospace;
}


nav a:hover {
  background-color: grey;
  color: lightgray;
}

.bottomList {
  position: absolute;
  bottom:0;
}

.footer {
  display: flex;
}

/* ----------------------------------------------------------------------- */
/* Main */
/* ----------------------------------------------------------------------- */

.Main {
  position: absolute;
  padding-top: 2rem;
}

.back-video {
  position: absolute;
  right: 0;
  bottom: 0;
  z-index: -1;
}

/* ----------------------------------------------------------------------- */
/* About */
/* ----------------------------------------------------------------------- */

.About {
  display: flex;
  padding-top: 2rem;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  margin-right: 30%;
  margin-left: 30%;
  background-color: white;
  border-radius: 10px;
  margin-top: 5rem;
  border: 1px solid lightgray;
}

.paragraphAbout {
  margin-left: 20px;
  margin-right: 20px;
}

/* ----------------------------------------------------------------------- */
/* SignInUp */
/* ----------------------------------------------------------------------- */
.SignIn {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  padding-top: 5vh;
}

.SignInInput {
  width: 200px;
  text-align: center;
  margin-bottom: 0.2rem;
  font-size: 1rem;
  border: 1px solid black;
  margin-bottom: 10px;
}

.sign {
  border: 1px solid black;
  background-color: white;
  transition: 0.3s;
}

.sign:hover {
  background-color: grey;
  color: lightgray;
}
</style>
