<template>
    <navBar
        :pages="pages"
        :active-page="activePage"
        :nav-link-click="(index) => activePage = index">
    </navBar>

    <pageViewer :page="pages[activePage]"></pageViewer>
</template>

<script>
import navBar from './components/navBar.vue';
import pageViewer from './components/pageViewer.vue';

export default {
    components: {
        navBar,
        pageViewer
    },
    data(){
        return{
            activePage: 0,
            pages: [
                {
                    link: {text: 'Home', url: 'index.html'},
                    pageTitle: 'Home',
                    pageContent: 'This is Home Content'
                },
                {
                    link: {text: 'Projects', url: 'projects.html'},
                    pageTitle: 'Projects',
                    pageContent: 'This is Projects Content'
                },
                {
                    link: {text: 'Contact', url: 'contact.html'},
                    pageTitle: 'Contact',
                    pageContent: 'This is Contact Content'
                },
                {
                    link: {text: 'Links', url: 'links.html'},
                    pageTitle: 'Links',
                    pageContent: 'This is Links Content'
                }
            ]
        };
    },
}
</script>