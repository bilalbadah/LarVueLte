<template>
    <div class="container">
        <div class="row justify-content-center">
            <div class="col-md-8">
                <div class="card">
                    <div class="card-header">Example Component</div>

                    <div class="card-body">
                        I'm an example component.
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        data(){
            return{
                posts : {}
            }
        },
        created() {
            this.getPosts();
        },
        methods: {
            getPosts(){
                axips.get("/api/posts")
                    .then(response => {
                        console.log(response.data);
                        this.posts = response.data;
                    })
                    .catch(err => console.log(err));
            }
        }
    }
</script>
