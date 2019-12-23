<template>
    <div id="app">

        <HelloWorld msg="Add here student details"/>
        <input type="text" v-model="name" placeholder="Enter Name"> <br>
        <input type="text" v-model="department" placeholder="Enter department"> <br>
       <button @click.prevent="addEmployee">Add employee</button>


<!--style/class binding-->

        <button v-on:click="fontSize++">
            Increase font size
        </button>
        <br>
        <button v-on:click="fontSize--">
            Decrease font size
        </button>
        <br>

        <p v-bind:style="{ fontSize: fontSize + 'px' }">
            The font size is: {{ fontSize }}
        </p>

<!--list rendering-->
        <table>
            <thead>
            <tr>
                <th>Name</th>
                <th>department</th>
            </tr>
            </thead>
            <tbody>
            <tr v-for="name in employees" :key="name" v-bind:item="employees">
                <td>{{name}}</td>
                <td>{{department}}</td>
            </tr>
            </tbody>
        </table>
    </div>
</template>

<script>
    import HelloWorld from './components/HelloWorld.vue'

    export default {
        name: 'app',
        components: {
            HelloWorld
        },
        data() {
            return {
                employees: [],
               std: [
                   { product: 'milk' },
                   { product: 'eggs' },
               ],
                name: '',
                department: '',
                fontSize: 10
            }

        },

        methods: {
            addEmployee: function () {
                this.employees.push(
                    this.name
                )

            }
        }
    }
</script>

<style>
    #app {
        font-family: 'Avenir', Helvetica, Arial, sans-serif;
        -webkit-font-smoothing: antialiased;
        -moz-osx-font-smoothing: grayscale;
        text-align: center;
        color: #2c3e50;
        margin-top: 60px;
    }

    button {
        width: 138px;
        height: 32px;
        background-color: turquoise;
        margin-top: 25px;
        color: black;
        letter-spacing: 2.5px;
        text-transform: uppercase;
        border-radius: 2px;
        box-shadow: 0px 10px 25px rgba(0, 0, 0, 0.1);
    }

    input {
        width: 308px;
        height: 37px;
        font-size: 15px;
        margin-bottom: 20px;
    }

    table{
        border-collapse: collapse;
        width: 80%;
        margin-top: 20px;
        margin-left:154px;
    }
    table td,th{
        border: 1px solid #ddd;
        padding: 8px;

    }

</style>
