<template>
    <div class="container d-flex justify-content-center p-4">
        <form>
            <div class="col-12">
                <label class="visually-hidden" for="inlineFormSelectPref">status</label>
                <select class="form-select" id="inlineFormSelectPref" v-model="search" @change="changed">
                    <option selected>Choose...</option>
                    <option :value="status" v-for="(status, index) in statusOptions" :key="index">{{status}}</option>
                </select>
            </div>

        </form>
    </div>
</template>

<script>
    export default {
        name:'SearchComponent',
        data() {
            return {
                statusOptions:[
                    'alive',
                    'deceased',
                    'presumed dead'
                ],
                search: ''
            }
        },
        // props:{
        //     searchStatus: String
        // },
        methods:{
            changed(){
               this.$emit('filterchar', this.search);

            }
        }
    }
</script>

<style lang="scss" scoped>

</style>