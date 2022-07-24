<template>
  <div>
    <h1>Create an event</h1>
    <form>
      <BaseSelect
        v-model="event.category"
        :options="categories"
        label="Select a category"
      />

      <h3>Name & describe your event</h3>

      <BaseInput
        v-model="event.title"
        label="Title"
      />

      <BaseInput
        v-model="event.description"
        label="Description"
      />

      <h3>Where is your event?</h3>

      <BaseInput
        v-model="event.location"
        label="Location"
        @click="handleClick()"
      />

      <h3>Are pets allowed?</h3>
      <div>
        <input type="radio" v-model="event.pets" :value="1" name="pets" />
        <label>Yes</label>
      </div>

      <div>
        <input type="radio" v-model="event.pets" :value="0" name="pets" />
        <label>No</label>
      </div>

      <h3>Extras</h3>
      <div>
        <input type="checkbox" v-model="event.extras.catering" class="field" />
        <label>Catering</label>
      </div>

      <div>
        <input type="checkbox" v-model="event.extras.music" class="field" />
        <label>Live music</label>
      </div>

      <button class="button -fill-gradient" type="submit">Submit</button>
    </form>
  </div>
</template>

<script>
import BaseInput from '../components/BaseInput.vue'
import BaseSelect from '../components/BaseSelect.vue'

export default {
  name: 'SimpleForm',
  components: { BaseInput, BaseSelect },
  data () {
    return {
      categories: [
        'sustainability',
        'nature',
        'animal welfare',
        'housing',
        'education',
        'food',
        'community'
      ],
      event: {
        category: '',
        title: '',
        description: '',
        location: '',
        pets: 1,
        extras: {
          catering: false,
          music: false
        }
      }
    }
  },
  methods: {
    handleClick () {
      console.log('test')
    }
  }
}
</script>
