<template>

    <div>
        <!-- use router-link component for navigation. -->
        <!-- specify the link by passing the `to` prop. -->
        <!-- `<router-link>` will be rendered as an `<a>` tag by default -->
        <nav class="navbar navbar-expand-md navbar-light bg-white shadow-sm">
        <div class="container">
            <router-link class="navbar-brand" :to="{ name: 'home'}">
                Boolpress
            </router-link>
            <button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#navbarSupportedContent" aria-controls="navbarSupportedContent" aria-expanded="false" aria-label="Toggle navigation">
                <span class="navbar-toggler-icon"></span>
            </button>

            <div class="collapse navbar-collapse" id="navbarSupportedContent">
                <!-- Left Side Of Navbar -->
                <ul class="navbar-nav mr-auto">
                    <li class="nav-item" v-for="item in menu_items" :key="item.route_name">
                        <router-link class="nav-link" :to="{ name: item.route_name }"> {{item.route_text}} </router-link>
                    </li>
                    
                </ul>

                <!-- Right Side Of Navbar -->
                <ul class="navbar-nav ms-auto">
                    <!-- Authentication Links -->
                    
                </ul>
            </div>
        </div>
    </nav>

        <!-- route outlet -->
        <!-- component matched by the route will render here -->
        <router-view></router-view>
    </div>

</template>

<script>
export default {
    name: 'App',
    data() {
        return {
            menu_items: [
                {
                    route_name: 'home',
                    route_text: 'home',
                },
                {
                    route_name: 'about',
                    route_text: 'about',
                },
                {
                    route_name: 'posts',
                    route_text: 'posts',
                }
            ]
        }
    }
}
</script>

