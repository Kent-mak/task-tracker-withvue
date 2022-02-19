<template>
    <div>
        <b-card @submit="onSubmit" >
            <b-form-group
                label-cols-lg="3"
                label="Add New Task"
                label-size="lg"
                label-class="font-weight-bold pt-0"
                class="mb-0"
            >
                <b-form-group
                    label="Task Name:"
                    label-for="nested-taskName"
                    label-cols-sm="3"
                    label-align-sm="right"
                >
                    <b-form-input id="nested-taskName" v-model="name"></b-form-input>
                </b-form-group>
                <!-- date -->
                <b-form-group
                    label="Due Date:"
                    label-for="nested-date"
                    label-cols-sm="3"
                    label-align-sm="right"
                >
                    <b-form-datepicker id="nested-date" v-model="date"></b-form-datepicker>
                </b-form-group>

                <!-- reminder -->
                <b-form-checkbox
                    id="checkbox-1"
                    v-model="reminder"
                    name="checkbox-1"
                    value=true
                    unchecked-value=false
                >
                Enable Reminder
                </b-form-checkbox>

            </b-form-group>

            <!-- save btn -->
            <b-button id="saveTask" block type="submit" >Save Task</b-button>

        </b-card>
    </div>
</template>

<script>
    export default {
        name: 'AddTask',
        data(){
            return{
                name: '',
                date: '',
                reminder: false
            }
        },
        methods: {
            onSubmit(event){
                event.preventDefault();
                
                if (!this.name){
                    alert('Please add a Task')
                }

                const newTask = {
                    name: this.name,
                    date: this.date,
                    reminder: this.reminder
                }

                this.$emit('add-task', newTask)

                this.name = ''
                this.date = ''
                this.reminder = false

            },
        }
    }
</script>

<style scoped>

</style>