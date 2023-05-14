<template>
    <div>
        <User :name="personJa.name" :salary="personJa.salary" :age="personJa.age" />
    </div>
</template>

<script>
import User from '../components/User/User.vue'
import { Customer } from '../models/customer';
export default {
    name: 'CustomerPage',
    components: { User },
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