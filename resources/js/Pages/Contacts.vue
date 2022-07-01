<template>
    
    <div class="page">
        <div class="p-5 bg-dark text-white">
            <div class="container">
                <div class="d-flex gap-4">
                    <div class="avatar">
                        <img class="rounded-circle" src="https://picsum.photos/200/200" alt="">
                    </div>
                    <div>
                        <h1 class="display-3">Contact me</h1>
                        <p class="lead">Lorem ipsum dolor sit amet, consectetur adipisicing elit. Quae, impedit!</p>
                    </div>
                </div>
                <hr class="my-2">
                <p>More info</p>
                <p class="lead">
                    <router-link class="btn btn-primary btn-lg" :to="{ name: 'posts' }">Read my blog</router-link>
                </p>
        </div>
        </div>
        <div class="container">
            <div class="content py-4">

                <vue-form method="PUT" action="/contact-form">
                
                    <div class="mb-3">
                        <label for="" class="form-label">Full Name</label>
                        <input type="text" name="full_name" id="full_name" class="form_control" placeholder="Mario Rossi" aria-describeby="fullnameHelper">
                        <small id="fullNameHelper" class="text-muted">Type your full name</small>
                    </div>
                    <div class="mb-3">
                        <label for="" class="form-label">Email</label>
                        <input type="text" name="email" id="email" class="form_control" placeholder="Mario Rossi" aria-describeby="emailHelper">
                        <small id="emailHelper" class="text-muted">Type youremail</small>
                    </div>
                    <div class="mb-3">
                        <label for="" class="form-label">Subject</label>
                        <input type="text" name="sunject" id="subject" class="form_control" placeholder="Mario Rossi" aria-describeby="subjectHelper">
                        <small id="subjectHelper" class="text-muted">Type your subject</small>
                    </div>
                    <div class="mb-3">
                        <label for="" class="form-label">Full Name</label>
                        <input type="text" id="full_name" class="form_control" placeholder="Mario Rossi" aria-describeby="fullnamehelper">
                        <small id="fullNameHelper" class="text-muted">Type your full name</small>
                    </div>

                </vue-form>

            </div>
        </div>
    </div>

</template>

<script>
import VueForm from '../components/VueForm.vue'
export default {
    name: 'Contacts',
    components: { VueForm }
}
</script>
