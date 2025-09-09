<template>
    <nav :class="[`navbar-${theme}`, `bg-${theme}`, 'navbar', 'navbar-expand-lg']">
        <div class="container-fluid">
            <a href="" class="navbar-brand">My Domain</a>
                <ul class="navbar-nav me-auto mb-2 mb-lg-0">
                    <li v-for="(page, index) in pages" class="nav-item" :key="index">
                        <navBarLink
                            :page="page"
                            :isActive="activePage == index"
                            @click.prevent="navLinkClick(index)"
                        ></navBarLink>
                    </li>
                </ul>
                <form action="" class="d-flex">
                    <button
                    class="btn btn-primary"
                    @click.prevent="changeTheme()">Mode</button>
                </form>
        </div>
    </nav>
</template>

<script>
import navBarLink from './navBarLink.vue';
export default {
    components: {
        navBarLink
    },
    props: ['pages', 'activePage', 'navLinkClick'],
    data(){
        return{
            theme: 'light',
        }
    },
    methods: {
        changeTheme() {
            let theme = 'light';

            if (this.theme == 'light'){
                theme = 'dark';
            }

            this.theme = theme;
            
        }
    }
}
</script>