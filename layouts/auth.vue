<template>
    <div>
        <div class="level px-4 is-mobile has-text-centered has-background-link ">
            <div class="level-left">

                <div class="level-item py-1">
                    <p class="has-text-white">Brand Portal</p>
    
                </div>
            </div>
            <div class="level-right">

                <div class="level-item py-1">
                    <p class="has-text-white is-underlined">Help?</p>
    
                </div>
            </div>
        </div>
        <section class="section hero pt-0 is-fullheight-with-navbar">
            <div class="hero-head">
                <div class="has-text-centered">

                    <figure class="container image pt-4" style="width:120px">
                        <img src="/logo.svg" alt="">
                    </figure>
                </div>
            </div>
            <div class="hero-body">
                <nuxt />

            </div>
            <div class="hero-footer">
                <div class="buttons is-centered">
                        <button class="button is-text">
                            FAQ
                        </button>
                        <button class="button is-text">
                            Terms & Conditions
                        </button>
                        <button class="button is-text">
                            Privacy
                        </button>
                </div>
            </div>
        </section>
    </div>
</template>

<script>
export default {
    name: 'auth',

}
</script>

<style>

</style>