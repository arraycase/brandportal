<template>
    <section class="is-fullheight">


       
        <div class=" is-relative">
         
            <div class="columns is-relative">
                <div class="column hero   is-fullheight is-fixed is-hidden-touch is-2 "
                    style="border-right:1px solid #dbdbdb;  ">
                   
                    <div class="hero-header pl-3 ">
                        <header class="  py-4">
                            <div class="media">
                                <div class="media-content">

                                    <figure class="image pt-3 ml-3 " style="width:120px">
                                        <img src="/logo.svg" alt="" class="">
                                    </figure>
                                </div>

                            </div>

                        </header>
                        <br>
                        <div class="   ">
                            <div class="  ">
                                <div>

                                    <nuxt-link class="menu-button is-fullwidth has-text-dark" to="/">
                                        <div class="media">
                                            <div class="media-left">
                                                <b-icon class="" icon="home-variant"></b-icon>
                                            </div>
                                            <div class="media-content is-size-6">
                                                Home
                                            </div>
                                        </div>

                                    </nuxt-link>
                                    <nuxt-link class="menu-button is-fullwidth" to="/">
                                        <div class="media">
                                            <div class="media-left">
                                                <b-icon icon="inbox"></b-icon>
                                            </div>
                                            <div class="media-content is-size-6">
                                                Orders
                                            </div>
                                        </div>

                                    </nuxt-link>
                                    <nuxt-link class="menu-button is-fullwidth" to="/">
                                        <div class="media">
                                            <div class="media-left">
                                                <b-icon icon="tag"></b-icon>
                                            </div>
                                            <div class="media-content is-size-6">
                                                Products
                                            </div>
                                        </div>

                                    </nuxt-link>
                                    <nuxt-link class="menu-button is-fullwidth" to="/">
                                        <div class="media">
                                            <div class="media-left">
                                                <b-icon icon="bookmark"></b-icon>
                                            </div>
                                            <div class="media-content is-size-6">
                                                Inventory
                                            </div>
                                        </div>

                                    </nuxt-link>
                                    <nuxt-link class="menu-button is-fullwidth" to="/">
                                        <div class="media">
                                            <div class="media-left">
                                                <b-icon icon="send"></b-icon>
                                            </div>
                                            <div class="media-content is-size-6">
                                                Campaigns
                                            </div>
                                        </div>

                                    </nuxt-link>
                                    <nuxt-link class="menu-button is-fullwidth" to="/">
                                        <div class="media">
                                            <div class="media-left">
                                                <b-icon icon="storefront"></b-icon>
                                            </div>
                                            <div class="media-content is-size-6">
                                                Storefront
                                            </div>
                                        </div>

                                    </nuxt-link>
                                    <nuxt-link class="menu-button is-fullwidth" to="/">
                                        <div class="media">
                                            <div class="media-left">
                                                <b-icon icon="account-multiple-outline"></b-icon>
                                            </div>
                                            <div class="media-content is-size-6">
                                                Customers
                                            </div>
                                        </div>

                                    </nuxt-link>
                                    <b-collapse animation="slide" aria-role="list">
                                        <template #trigger="{ active }">
                                            <nuxt-link class="menu-button is-fullwidth has-text-dark" to="/">

                                                <div class="media">
                                                    <div class="media-left">
                                                        <b-icon class="" icon="layers"></b-icon>
                                                    </div>
                                                    <div class="media-content is-size-6">
                                                        Masters
                                                    </div>
                                                    <div class="media-right">
                                                        <b-icon class="" icon="chevron-down"></b-icon>
                                                    </div>
                                                </div>

                                            </nuxt-link>
                                        </template>

                                        <div class="">
                                            <nuxt-link class="menu-button is-fullwidth has-text-dark" to="/">

                                                <div class="media">
                                                    <div class="media-left">
                                                        <!-- <b-icon class="" icon="tune"></b-icon> -->
                                                    </div>
                                                    <div class="media-content is-size-6">
                                                        Product Category
                                                    </div>
                                                </div>


                                            </nuxt-link>
                                            <nuxt-link class="menu-button is-fullwidth has-text-dark" to="/masters/hsn">

                                                <div class="media">
                                                    <div class="media-left">
                                                        <!-- <b-icon class="" icon="tune"></b-icon> -->
                                                    </div>
                                                    <div class="media-content is-size-6">
                                                        HSN
                                                    </div>
                                                </div>
                                            </nuxt-link>
                                            <nuxt-link class="menu-button is-fullwidth has-text-dark" to="/">

                                                <div class="media">
                                                    <div class="media-left">
                                                        <!-- <b-icon class="" icon="tune"></b-icon> -->
                                                    </div>
                                                    <div class="media-content is-size-6">
                                                        UOM
                                                    </div>
                                                </div>
                                            </nuxt-link>
                                            <nuxt-link class="menu-button is-fullwidth has-text-dark" to="/">

                                                <div class="media">
                                                    <div class="media-left">
                                                        <!-- <b-icon class="" icon="tune"></b-icon> -->
                                                    </div>
                                                    <div class="media-content is-size-6">
                                                        Variants
                                                    </div>
                                                </div>
                                            </nuxt-link>
                                            <nuxt-link class="menu-button is-fullwidth has-text-dark" to="/">

                                                <div class="media">
                                                    <div class="media-left">
                                                        <!-- <b-icon class="" icon="tune"></b-icon> -->
                                                    </div>
                                                    <div class="media-content is-size-6">
                                                        Filters
                                                    </div>
                                                </div>
                                            </nuxt-link>
                                            <nuxt-link class="menu-button is-fullwidth has-text-dark" to="/">

                                                <div class="media">
                                                    <div class="media-left">
                                                        <!-- <b-icon class="" icon="tune"></b-icon> -->
                                                    </div>
                                                    <div class="media-content is-size-6">
                                                        Company
                                                    </div>
                                                </div>
                                            </nuxt-link>
                                        </div>

                                    </b-collapse>

                                    <nuxt-link class="menu-button is-fullwidth has-text-dark" to="/">

                                        <div class="media">
                                            <div class="media-left">
                                                <b-icon class="" icon="tune"></b-icon>
                                            </div>
                                            <div class="media-content is-size-6">
                                                Settings
                                            </div>
                                        </div>

                                    </nuxt-link>
                                </div>


                            </div>
                        </div>
                    </div>

                    <div class="hero-footer pl-3">

                        <nuxt-link class="menu-button is-fullwidth has-text-dark" to="/">

                            <div class="media">
                                <div class="media-left">
                                    <b-icon class="" icon="help-circle"></b-icon>
                                </div>
                                <div class="media-content is-size-6">
                                    Help
                                </div>
                            </div>

                        </nuxt-link>
                        <nuxt-link class="menu-button is-fullwidth has-text-dark" to="/">

                            <div class="media">
                                <div class="media-left">
                                    <b-icon class="" icon="face-agent"></b-icon>
                                </div>
                                <div class="media-content is-size-6">
                                    Support
                                </div>
                            </div>

                        </nuxt-link>


                    </div>
                </div>
                <div class="column ">
                   
                    <div class="section">
                        <nuxt />
                    </div>
                </div>
            </div>
        </div>
    </section>
</template>
  
<script>
export default {
    name: "admin",
    // middleware: ["auth"],
    methods: {
        async logout() {
            await this.$auth.logout().then((response) => {
                this.$router.push("/auth");
            });
        },
   
    },
};
</script>
<style>

.box-dumb {
    box-shadow: none !important;
    border: 1px solid #dbdbdb;
}

.div-is-fullheight {
    height: 100vh;
}

.has-background-dark-array {
    /* background-color: 2a2e31; */
}

.unselectable-text {
    -webkit-user-select: none;
    /* Safari */
    -moz-user-select: none;
    /* Firefox */
    -ms-user-select: none;
    /* IE10+/Edge */
    user-select: none;
}

* {
    font-family: 'Figtree', sans-serif !important;

}

/* .button {
    font-family: 'DM Mono', 'Courier New', Courier, monospace !important;
    font-weight: 600;

} */

html {
    /* background-color: #fefefe; */
}

/* section {
    height: 100%;
} */

hr {
    background-color: #90c9c79a;
    height: 1px;
}

ul>li {
    /* border-bottom: 1px solid #90c9c79a; */
    padding: 0.2rem 0 0.5rem 0;
}

.hero-body-scroll {
    /* max-height: 80%; */

    /* overflow: auto;
    overflow-x: hidden;
    overflow-y: scroll; */
}


/* .bottom-element{
    position: fixed;
    bottom:0;
    width: 100%;
    background-color: #fff;
    padding: 1rem;
} */

.small-dot {
    margin: auto;
    width: 10px;
    height: 10px;
    border-radius: 50px;
    background-color: blue;
}

html {
    scroll-behavior: smooth;
}

.sidebar-content-body {
    display: flex;
    flex-direction: column;
}

/* input[type="text-number"]{
    font-family: 'IBM Plex Mono', Courier, monospace !important; 
    font-weight: 500 important; 
}
input[type="number"]{
    font-family: 'IBM Plex Mono', Courier, monospace !important; 
    font-weight: 500 important; 
} */

.b-sidebar .sidebar-content {
    min-width: 450px !important;
}

.sidebar-content-main {
    min-height: 100%;
    flex: 1;
}

.menu-button {
    /* font-weight: 600; */
    /* width: 100%; */
    /* font-size:12x; */
    padding-left: calc(0.7em - 1px);
    padding-right: calc(0.7em - 1px);
    cursor: pointer;
    justify-content: left;
    padding-bottom: calc(0.5em - 1px);

    margin-top: calc(0.1em - 1px);
    padding-top: calc(0.5em - 1px);
    text-align: left;
    display: block;
    white-space: nowrap;
    font-size: 15px;
    width: 100%;
    font-weight: 400 !important;

    transition: 0.2s all ease-in;
}

.menu-button .dropdown-trigger {
    width: 100%;
}

.menu-button-center {
    color: #3d3d3d;
    cursor: pointer;

    justify-content: center;
    padding-top: calc(0.6em - 1px);
    padding-bottom: calc(0.6em - 1px);
    text-align: center;
    display: block;
    white-space: nowrap;
    border-radius: 7px;
    transition: 0.2s all ease-in;
}

.menu-button-center:hover {
    background-color: rgb(228, 228, 228);
    /* font-weight: 800 !important; */
    color: #0a0a0a !important;
}

/* .menu-button-bottom{
    position: relative ;
    width:100%;
    bottom: 0;
} */

.menu-button:hover {
    background-color: rgba(228, 228, 228, 0.87);
    border-radius: 5px;
    color: #000 !important;
}

.sub-nav .button-x {
    padding: 10px 10px;
    font-weight: 300 !important;
}

.sub-nav .button-x:hover {
    font-weight: 300;
}

.menu-burger {
    cursor: pointer;
    display: block;
    height: 3.25rem;
    position: relative;
    width: 3.25rem;
    margin-left: auto;
    padding: 10px 10px 5px 0;
}

.is-family-monospace {
    font-family: "Roboto Mono";
    text-transform: uppercase;
}

.th-wrap {
    color: black;
    font-weight: 600;
}

.modal-content {
    overflow-y: auto !important;
}

.fade-enter-active,
.fade-leave-active {
    transition: opacity 0.5s;
}

.fade-enter,
.fade-leave-active {
    opacity: 0;
}

li {
    list-style: none;
}

.has-border-link-light {
    border-radius: 5px;
    border: 1px solid rgba(0, 0, 0, 0.6);
    border-right: 5px solid rgba(0, 0, 0, 0.6);
    background-color: #eee;
}

.pattern-plus {
    background-color: #ffffff;
    background-image: url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='4' height='4' viewBox='0 0 4 4'%3E%3Cpath fill='%23dbdbdb' fill-opacity='0.4' d='M1 3h1v1H1V3zm2-2h1v1H3V1z'%3E%3C/path%3E%3C/svg%3E");
}

.tabs ul {
    -webkit-box-align: center;
    -ms-flex-align: center;
    align-items: center;
    border-bottom-color: none !important;
    border-bottom-style: none !important;
    border-bottom-width: none !important;
    display: -webkit-box;
    display: -ms-flexbox;
    display: flex;
    -webkit-box-flex: 1;
    -ms-flex-positive: 1;
    flex-grow: 1;
    -ms-flex-negative: 0;
    flex-shrink: 0;
    -webkit-box-pack: start;
    -ms-flex-pack: start;
    justify-content: flex-start;
}
</style>
  