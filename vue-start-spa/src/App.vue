<template>
    <navbar
        :pages="pages"
        :activePage="activePage"
        :nav-link-click="(index)=>activePage=index"
    ></navbar>

    <page-viewer
        :page="pages[activePage]"
    ></page-viewer>
</template>

<script>
import Navbar from "./components/Navbar.vue";
import PageViewer from "./components/PageViewer.vue";

export default {
    components: {
        Navbar,
        PageViewer, 
    },
    data() {
        return {
            activePage: 0,
            pages: [
                {
                    link: {text: "Home", url: "index.html"},
                    pageTitle: "Home Page",
                    content: "This is home page content."
                },
                {
                    link: {text: "About", url: "about.html"},
                    pageTitle: "About Page",
                    content: "This is about page content."
                },
                {
                    link: {text: "Contact", url: "contact.html"},
                    pageTitle: "Contact Page",
                    content: "This is contact page content."
                }
            ]
        }
    }
}
</script>