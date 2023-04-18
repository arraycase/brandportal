<template>

    <div class="column is-4-desktop is-3-fullscreen is-10-touch is-4-tablet">
        <div>
            <div class="">
                <div class="has-text-centered">

                    <p class="title is-size-4">
                        B2B selling shouldn't be tough
                    </p>
                    <p class="subtitle is-size-4">
                        Let's make it easy for you
                    </p>
                   
                </div>
                <br>
                <br>
                <div>

                    <b-field label="Name">
                        <b-input placeholder="Your Name"></b-input>
                    </b-field>
                    <b-field label="Contact">
                        <b-input placeholder="Your Contact Number"></b-input>
                    </b-field>
                    <b-field label="Email">
                        <b-input type="email" placeholder="Your Email"></b-input>
                    </b-field>
                    <b-field label="Password">
                        <b-input placeholder="Enter Password" type="password"></b-input>
                    </b-field>
                    <b-field label="Industry">
                        <b-autocomplete icon="magnify" placeholder="Select Your Industry">

                        </b-autocomplete>
                    </b-field>
                    <div class="level">
                        <div class="level-left">
                        </div>
                        <div class="level-right">
                            <div class="level-item">
                                <button class="button is-black">
                                    Save & Next <b-icon class="ml-2" icon="chevron-right"></b-icon>
                                </button>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
layout:'onboarding'
}
</script>

<style>

</style>