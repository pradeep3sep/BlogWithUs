<template>
    <div class="home">
        <blog-post :post='welcomeScreen' />
        <blog-post v-for="(post,index) in sampleBlogPost" :key="index" :post="post" />
        <div class="blog-card-wrap">
            <div class="container">
                <h3>View More Recents Blogs</h3>
                <div class="blog-cards row">
                    <blogCards class="col-md-6 col-sm-12" :post="post" v-for="(post,index) in sampleBlogCards" :key="index"/>
                </div>
            </div>
        </div>
        <div class="updates" v-if="!this.$store.state.profileInitials">
            <div class="container">
                <div class="row">
                    <div class="col-8 heading">
                        <h2>NEVER MISS A POST. REGISTER FOR YOUR FREE ACCOUNT TODAY!</h2>
                    </div>
                    <router-link to="/blogs" class="router-button col-4 button-desktop">
                        Register for FireBlog <img src="../assets/arrow-right-light.svg" alt="" srcset="" class="arrow">
                    </router-link>
                </div>
            </div>
        </div>
    </div>
</template>
<script>
import blogPost from './blogPost.vue'
import blogCards from './blogCards.vue'
export default {
    data() {
        return {
            welcomeScreen: {
                title: "Welcome",
                blogPost: "Weekly blog articles with all things programming including HTML, CSS, Javascript and mor. Register today to never miss a post",
                welcomeScreen: true,
                photo: "coding",
            },
            sampleBlogPost: [
                {
                    title: "This is a Filter Title!",
                    blogHTML: "This is a Filter Blog Post Title!",
                    blogCoverPhoto: "beautiful-stories"
                },
                {
                    title: "This is a Filter Title!",
                    blogHTML: "This is a Filter Blog Post Title!",
                    blogCoverPhoto: "designed-for-everyone"
                },
            
            ],
        }
    },
    computed: {
        sampleBlogCards () {
            return this.$store.state.sampleBlogCards
        },
    },
    components: {
        blogPost,
        blogCards,
    }
}
</script>
<style>
    
</style>