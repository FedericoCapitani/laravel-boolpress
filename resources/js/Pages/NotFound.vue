<template>
    
    <div class="page">
        <div class="p-5 bg-dark text-white">
            <div class="container">
                <div class="d-flex g-4">
                    <div class="avatar">
                        <img class="rounded-circle" src="https://picsum.photos/200/200" alt="">
                    </div>
                    <div>
                        <h1 class="display-3">Oops! Page not found, 404</h1>
                        <p class="lead">Sorry, the page you requested doesn't exist.</p>
                    </div>
                </div>
            </div>
        </div>
        <div class="container">
            <div class="content py-4">
                Te page you requested was not found, try to visit these pages
                <ul>
                    <li>
                        <router-link :to="{ name: 'home' }">HomePage</router-link>
                    </li>
                    <li>
                        <router-link :to="{ name: 'about' }">About</router-link>
                    </li>
                    <li>
                        <router-link :to="{ name: 'posts' }">Posts</router-link>
                    </li>
                </ul>    
            </div>
        </div>
    </div>

</template>

<script>
export default {
    name: 'NotFound'
}
</script>
