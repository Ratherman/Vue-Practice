<template>
    <form action="" class="container mb-3">
        <div class="row">
            <div class="col-md-8">
                <div class="mb-3">
                <label for="" class="form-label">
                    Page Title
                </label>
                <input 
                    type="text"
                    class="form-control"
                    v-model="pageTitle"
                />
            </div>

            <div class="mb-3">
                <label for="" class="form-label">
                    Content
                </label>
                <textarea 
                    class="form-control"
                    rows="5"
                    v-model="content"
                ></textarea>
            </div>
        </div>

        <div class="col">

            <div class="mb-3">
                <label for="" class="form-label">
                    Link Text
                </label>
                <input
                    type="text"
                    class="form-control"
                    v-model="LinkText"
                />
            </div>

            <div class="mb-3">
                <label for="" class="form-label">
                    Link URL
                </label>
                <input
                    type="text"
                    class="form-control"
                    v-model="LinkURL"
                />
            </div>

            <div class="row mb-3">
                <div class="form-check">
                    <input class="form-check-input" type="checkbox">
                    <label class="form-check-label" for="gridCheck1">
                        Published
                    </label>
                </div>
                
            </div>
        </div>
        </div>
        <div class="mb-3">
            <button 
                class="btn btn-primary"
                @click.prevent="submitForm"
                :disabled="isFormInvalid"
            >Create Page</button>
        </div>
    </form>
    
</template>
<script>
export default {
    props: ["pageCreated"],
    computed: {
        isFormInvalid(){
            return !this.pageTitle || !this.content || !this.LinkText || !this.LinkURL;
        }
    },
    data(){
        return {
            pageTitle: "",
            content: "",
            LinkText: "",
            LinkURL: ""
        }
    },
    methods:{
        submitForm(){
            if (!this.pageTitle || !this.content || !this.LinkText || !this.LinkURL){
                alert("Please fill out all fields")
                return;
            }

            this.pageCreated({
                title: this.pageTitle,
                content: this.content,
                link: {
                    text: this.LinkText,
                    url: this.LinkURL
                }
            })
        }
    }
}   
</script>