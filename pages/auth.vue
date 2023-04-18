<template>
    <!-- <div> -->

        <div class="container ">
            
            <div class="columns  is-mobile is-centered">
                <div class="column is-4-desktop">
                    <b-field expanded label="Username">
            
                        <b-input expanded placeholder="Enter Phone Number/ Email"></b-input>
                    </b-field>
                    <b-field label="Password">
            
                        <b-input placeholder="Enter Password"></b-input>
                    </b-field>
                    <b-button class="is-fullwidth button is-black">
                        Log in
                    </b-button>
                    <p class="mt-2 ">
            
                        <n-link to="/" class="has-text-grey">
                            Forgot Password ?
                        </n-link>
                    </p>
                    <br>
                    <b-button class="is-fullwidth button is-black is-outlined">
                        Create a New Account
                    </b-button>
    
                </div>
            </div>
        </div>
        
        











    <!-- </div> -->
</template>

<script>
export default {
    layout: 'auth',
}
</script>

<style>

</style>