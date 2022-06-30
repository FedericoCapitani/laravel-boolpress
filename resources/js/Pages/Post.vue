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

            <div class="no-tags" v-else> 
                <strong>Tags: N/A</strong>
            </div>

            <div class="author" v-if="post.user">
                <strong>Author: </strong> {{post.user.name}}
            </div>

        </div>

    </div>

</template>

<script>
export default {
    name: 'Post',
    data() {
        return {
            post: ''
        }
    },
    mounted(){
        axios.get('/api/posts/' + this.$route.params.slug)
        .then(response => {
            console.log(response);
            this.post = response.data;
        })
        .catch(e => {
            console.error(e);
        })
    }
}
</script>

<style lang="scss">

</style>