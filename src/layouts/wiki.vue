<template>
    <div>
        <Navbar />
        <div class="section">
            <div class="container">
                <div class="columns">
                    <div class="column is-3">
                        <WikiMenu />
                    </div>
                    <div class="column">
                        <div class="container">
                            <div class="content">
                                <slot name="default" />
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
        <Footer />
    </div>
</template>

<script>
import Navbar from "../components/Navbar.vue";
import Footer from "../components/Footer.vue";
import WikiMenu from "../components/WikiMenu.vue";

export default {
    props: ['page'],
    components: {
        Navbar,
        Footer,
        WikiMenu
    },
    head() {
        return {
            title: `${this.page.attributes.title} - ${this.$siteConfig.title} Wiki`
        }
    }
}
</script>
