<template>
    <div>
        <TopNav />
        <User :name="personJa.name" :salary="personJa.salary" :age="personJa.age" />
    </div>
</template>

<script>
import TopNav from '../components/Nav/TopNav.vue'
import User from '../components/User/User.vue'
import { Customer } from '../models/customer';
export default {
    name: 'CustomerPage',
    components: { TopNav, User },
    data() {
      return {
        personJa: null,
      }
    },
    created() {
      this.personJa = this.person('ja', 'zilion', '22');
    },
    methods: {
        person(imie, salary, age) {
            return new Customer(imie, salary, age);
        }
    }
}
</script>
<style scoped>

</style>