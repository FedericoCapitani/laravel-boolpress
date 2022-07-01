<template>
    
     <div class="single-page">

        <div class="container">

            <img class="img-fluid w-100" :src="post.image" :alt="post.title">
            <h1> {{post.title}} </h1>

            <div class="content">
                {{post.body}}
            </div>

            <div class="category" v-if="post.category">
                Category: {{post.category.name}}
            </div>

            <div class="tags" v-if="post.tags">
                <strong>Tags: </strong>
                <ul>
                    <li v-for="tag in post.tags" :key="tag.id"> {{tag.title}} </li>
                </ul>

            </div>

            <div class="author" v-if="post.user">
                <strong>Author: </strong> {{post.user.name}}
            </div>

        </div>

    </div>

</template>

<script>
import Axios from "axios";
export default {
    name: "Post",
    data() {
        return {
        post: "",
        loading:true
        };
    },
    created() {
        Axios.get("/api/posts/" + this.$route.params.slug)
        .then((response) => {
            console.log(response)
            if(response.data.status_code === 404) {
                this.$router.push({name:'not-found'})
            } else {
                this.post = response.data;
                this.loading = false
            }
        })
        .catch((e) => {
            console.error(e);
        });
    },
};
</script>

<style lang="scss" scoped>
    .hero_image{
        height: 600px;
        background-color: rgba(0, 0, 0, 0.464);
        background-blend-mode: overlay;
    }
</style>