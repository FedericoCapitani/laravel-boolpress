<template>
    
    <div class="page">

        <div class="p-5 bg-dark text-white">
            <div class="container">
                <h1 class="display-3">Boolpress Blog</h1>
                <p class="lead">Lorem ipsum, dolor sit amet consectetur adipisicing elit. Illum, nemo?</p>
            </div>
        </div>

        <section class="recent_articles">

            <div class="container">

                <div class="row pt-4">
                    <div class="col" v-for="post in posts" :key="post.id">
                        <div class="card">
                            <img :src="post.image" alt="">
                            <div class="card-body">
                                <p>
                                    {{post.body.slice(0, 200)}}
                                </p>
                                <a href="#">Read more</a>
                            </div>
                        </div>
                    </div>
                </div>
                <div class="go_to_blog mt-5 ">
                    <router-link class="btn btn-primary btn-lg" :to="{ name: 'posts' }">Read my blog</router-link>
                </div>
            </div>


        </section>

    </div>

</template>

<script>
export default {
    name: 'Home',
    data() {
        return {
            posts: ''
        }
    },
    methods: {

    },
    mounted() {
        axios.get('/api/posts')
        .then(response => {
            console.log(response.data);
            const posts = response.data;
            this.posts = posts.data.slice(0,4);    
        })
        .catch(e => {
            console.error(e);
        })
    }
}
</script>
