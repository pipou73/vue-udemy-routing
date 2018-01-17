<template>
    <div>
        <h3>Some User Details</h3>
        <p>User loaded has Id : {{ $route.params.id }}</p>
        <!--:to="'/user/' + $route.params.id + '/edit' "-->
        <router-link
                tag="button"
                :to="link"
                class="btn btn-primary">Edit User
        </router-link>
    </div>
</template>

<script>
    export default {
        data() {
            return {
                link: {
                    name: 'userEdit',
                    params: {
                        id: this.$route.params.id
                    } ,
                    query: {
                        locale: 'en',
                        q: 1000
                    },
                    hash: '#data'
                }
            }
        },
        beforeRouteEnter(to, from, next) {
            if (false) {
                next(vm => {
                    console.log(vm)
                });
            } else {
                next();
            }
        }
    }
</script>