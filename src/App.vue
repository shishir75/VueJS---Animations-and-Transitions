<template>
    <div class="container my-5">
        <div class="row">
            <div class="col0-xs-12 col-sm-8 offset-sm-2 col-md-6 offset-md-3">
                <h1>Animations</h1>
                <hr>
                <button class="btn btn-primary" @click="show = !show">Show Alert</button>
                <transition name="fade">
                    <div class="alert alert-info mt-3" v-if="show">
                        This ia an Info Alert!
                    </div>
                </transition>

                <transition name="slide" type="animation">
                    <div class="alert alert-info mt-3" v-if="show">
                        This ia an Info Alert!
                    </div>
                </transition>

                <transition name="fade" appear>
                    <div class="alert alert-info mt-3" v-if="show">
                        This ia an Info Alert!
                    </div>
                </transition>

            </div>
        </div>

    </div>
</template>

<script>

export default {
    name: 'App',
    data() {
        return {
            show: true
        }
    }


}
</script>

<style>
    .fade-enter {
        opacity: 0;
    }
    .fade-enter-active {
        transition: opacity 1s;
    }
    .fade-leave {

    }
    .fade-leave-active {
        transition: opacity 1s;
        opacity: 0;
    }

    .slide-enter {
        opacity: 0;
    }
    .slide-enter-active {
        animation: slide-in 1s ease-out forwards;
        transition: opacity 0.5s;
    }
    .slide-leave {

    }
    .slide-leave-active {
        animation: slide-out 1s ease-out forwards;
        transition: opacity 3s;
        opacity: 0;
    }

    @keyframes slide-in {
        from {
            transform: translateY(20px);
        }
        to {
            transform: translateY(0);
        }
    }

    @keyframes slide-out {
        from {
            transform: translateY(0);
        }
        to {
            transform: translateY(20px);
        }
    }
</style>
