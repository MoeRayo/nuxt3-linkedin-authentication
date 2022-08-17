<template>
  <div class="bg-lightest-blue vh-100 pa3 tc">
    <h2 class="black ttc">LinkedIn authentication with Appwrite</h2>
    <div class="br3 bg-dark-blue ba near-white b--black-10 shadow-3 w-100 w-60-m w-30-l mw6 center mt5 ph4 pv4">
      <p class="f3">Click on this button to login</p>
        <button class="link dim br3 pv2 ph2 mb2 dib black fw6 bg-white ba b--navy pointer mt3 mt0-l inline-flex items-center" @click="loginWithLinkedin">
          <span class="f4 ml2 pr2">Login with Linkedin</span>
        </button>
    </div>
  </div>
</template>

<script lang="ts">
import {sdk} from '~/init'
export default {
  methods: {
    loginWithLinkedin: async function(){
      try {
        await sdk.account.createOAuth2Session('linkedin', 'http://localhost:3000/dashboard')
      } catch (error) {
        console.log(error)
      }
    }
  }
}

</script>
