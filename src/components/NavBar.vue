<template>
    <b-navbar toggleable="md" type="dark" variant="info" sticky v-bind:class="{shrink:Escroleando}  ">
        <b-navbar-brand href="/">This is only for testing if the navbar shrink on scroll</b-navbar-brand>
        <b-navbar-nav>
            <b-nav-item to="/">Search</b-nav-item>
        </b-navbar-nav>
        <b-navbar-nav class="ml-auto">
            <b-nav-text type="light" right>
                version 0.1
            </b-nav-text>
        </b-navbar-nav>
    </b-navbar>
</template>

<script>
    export default {
        name: 'barra-navegacion',
        data() {
            return {
                Escroleando: false
            }
        },
        methods: {
            resizeOnScroll: function () {
                this.Escroleando = (window.scrollY >= 20);
                console.debug("Escroleando: " + this.Escroleando);
            }
        },
        created() {
            window.addEventListener('scroll', this.resizeOnScroll)
        },
        destroyed() {
            window.addEventListener('scroll', this.resizeOnScroll)
        }
    }
</script>

<style>
    nav.navbar.shrink {
        max-height: 10px;
    }
</style>
