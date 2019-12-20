<template>
    <div>
    <b-container style="padding-bottom: 30px">
        <b-jumbotron header="A Single Source For Education" style="text-align: center">
        <hr class="my-4">
            <img src='nz.svg' alt="nz" height="150" style="fill: blue"/>
            <p>Sign up to begin your learning journey</p>

            <div>
                <b-button v-b-modal.modal-prevent-closing style="background-color: teal">Sign Up</b-button>

                <div class="mt-3">
                Submitted Names:
                <div v-if="submittedNames.length === 0">--</div>
                <ul v-else class="mb-0 pl-3">
                    <li v-for="name in submittedNames" v-bind:key="{ name }">{{ name }}</li>
                </ul>
                </div>

                <b-modal
                id="modal-prevent-closing"
                ref="modal"
                title="Submit Your Name"
                @show="resetModal"
                @hidden="resetModal"
                @ok="handleOk"
                >
                <form ref="form" @submit.stop.prevent="handleSubmit">
                    <b-form-group
                    :state="nameState"
                    label="Name"
                    label-for="name-input"
                    invalid-feedback="Name is required"
                    >
                    <b-form-input
                        id="name-input"
                        v-model="name"
                        :state="nameState"
                        required
                    ></b-form-input>
                    </b-form-group>
                </form>
                </b-modal>
            </div>

        </b-jumbotron>

        <b-row >
            <b-col>
            <b-card 
                bg-variant="dark" 
                text-variant="white" 
                title="Our Goal"
                img-src="/learning.png"
                style="max-width: 35rem;"
            >
                <b-card-text>
                    Everybody learns is an academic platform for NZQA papers, where all content is taught by some of the best teachers in New Zealand.
                </b-card-text>

                <b-card-text>
                    We aim to expand accessability to learning resources with the goal that anyone and everyone that wants to learn, can learn.
                </b-card-text>

        <b-button id="show-btn" @click="$bvModal.show('bv-modal-example')">Open Modal</b-button>

        <b-modal id="bv-modal-example" hide-footer size="xl" centered>
            <template v-slot:modal-title>
                Watch Our Intro Video!
            </template>
            <div class="d-block text-center">
                <iframe width="765" height="450" src="https://www.youtube.com/embed/tyV0vZPqr1U" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
            </div>
            <b-button class="mt-3" block @click="$bvModal.hide('bv-modal-example')">Close Me</b-button>
        </b-modal>
                
            </b-card>
            </b-col>




            <b-col>
                <b-card bg-variant="dark" text-variant="white" title="Card Title">
                    <b-card-text>
                        With supporting text below as a natural lead-in to additional content.
                    </b-card-text>

                    <b-button href="#" variant="primary">Go somewhere</b-button>
                    
                </b-card>
            </b-col>
        </b-row>

    <div>
        
    </div>

    </b-container>
    <Footer />
    </div>

</template>

<script>
import Footer from './Footer.vue'

export default {
    data() {
      return {
        name: '',
        nameState: null,
        submittedNames: []
      }
    },
    components: {
        Footer
    },
    methods: {
      checkFormValidity() {
        const valid = this.$refs.form.checkValidity()
        this.nameState = valid ? 'valid' : 'invalid'
        return valid
      },
      resetModal() {
        this.name = ''
        this.nameState = null
      },
      handleOk(bvModalEvt) {
        // Prevent modal from closing
        bvModalEvt.preventDefault()
        // Trigger submit handler
        this.handleSubmit()
      },
      handleSubmit() {
        // Exit when the form isn't valid
        if (!this.checkFormValidity()) {
          return
        }
        // Push the name to submitted names
        this.submittedNames.push(this.name)
        // Hide the modal manually
        this.$nextTick(() => {
          this.$refs.modal.hide()
        })
      }
    }
}
</script>

<style scoped>

</style>