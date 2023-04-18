<template>
    <section class="is-fullheight">


        <div class="has-text-centered">

            <figure class="container image pt-4" style="width:120px">
                <img src="/logo.svg" alt="">
            </figure>
        </div>
        <div class="columns  is-mobile is-centered" style="border-bottom: 0.5px solid #dbdbdb">
            <div class="column is-4-desktop">

                <div class="level is-mobile container has-background-white is-mobile mt-4 px-4 pt-2 pb-2">

                    <div class="level-item">
                        About
                    </div>
                    <div class="level-item ">
                        Plans
                    </div>
                    <div class="level-item ">
                        Company
                    </div>
                    <div class="level-item ">
                        Branding
                    </div>


                </div>
            </div>
        </div>
        <div class="columns section div-is-fullheight is-mobile is-centered">
           <nuxt/>
        </div>


    </section>
</template>
  
<script>
export default {
    name: "onboarding",
    // middleware: ["auth"],
    data() {
        return {
            pageTab: 0,
        }
    },
    methods: {
        async logout() {
            await this.$auth.logout().then((response) => {
                this.$router.push("/auth");
            });
        },
        syncData() {
            this.$axios.get("/basic_master/sync").then((response) => {
                this.$buefy.snackbar.open({
                    duration: 4000,
                    message: response.data.success,
                    type: "is-light",
                    position: "is-top-right",
                    actionText: "Close",
                    queue: true,
                    onAction: () => {
                        this.isActive = false;
                    },
                });
            });
        },
    },
};
</script>
<style>
@import url('https://fonts.googleapis.com/css2?family=Manrope:wght@400;600&display=swap');

.box-dumb {
    box-shadow: none !important;
    border: 1px solid #dbdbdb;
}

.div-is-fullheight {
    height: 100vh;
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
    font-family: 'Inter', sans-serif !important;

}

/* .button {
    font-family: 'DM Mono', 'Courier New', Courier, monospace !important;
    font-weight: 600;

} */

html {
    /* background-color: #fefefe; */
}

section {
    height: 100%;
}

hr {
    background-color: #90c9c79a;
    height: 1px;
}

ul>li {
    /* border-bottom: 1px solid #90c9c79a; */
    padding: 0.2rem 0 0.5rem 0;
}

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

.b-sidebar .sidebar-content {
    min-width: 450px !important;
}

.sidebar-content-main {
    min-height: 100%;
    flex: 1;
}

.menu-button {
    color: #3d3d3d;
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
    vertical-align: top;
    display: block;
    white-space: nowrap;
    font-size: 15px;
    font-weight: 600 !important;

    transition: 0.2s all ease-in;
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
  