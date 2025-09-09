<template>
    <a
        :href="page.link.url"
        :title="`This link goes to the ${page.link.text} page`"
        class="nav-link"
        :class="{active: activePage == index}"
        aria-current="page">
        {{ page.link.text }}</a>
</template>

<script>
export default {
    props: ['page', 'isActive'],
    computed: {
        activeClasses(){
            return{
                active: this.isActive,
                emphasize: this.isActive
            }
        }
    }
}
</script>