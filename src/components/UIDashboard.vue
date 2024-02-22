<template>
  <v-container>
    <!-- component used to create dynamic heading -->
    <v-row>
      <Heading tag="h2" class="headingClass">
        Form Elements
      </Heading>
      
      <Heading tag="h4" class="headingClass">
        Go through<a href="https://v2.vuetifyjs.com/en/getting-started/installation/"> Vuetify 2.6.0</a>  to check UI Component in More detailed way
      </Heading>
      
    </v-row>
    <v-row >
      <v-col class="col-3 elevation-1">
        <InputField v-for="input in inputs" :key="input.id" v-model="input.value" :disabled="input.isDisable"
          :label="input.label" :placeholder="input.placeholder" :type="input.type" :prepend-inner-icon="input.prependicon"
          :append-icon="input.appendicon" solo :rules="input.rules" :hint="input.hint"></InputField>
      </v-col>
      <v-col class="col-4 elevation-1">
        <DropDown rounded solo :items="items" auto-select-first />
        <DatePicker range :value="date" />
      </v-col>
      <v-col class="col-5 elevation-1">
        <Heading tag="h5" class="headingClass">Toast </Heading>
        <Toast v-for="toast in toastItems" :key="toast.id" :type="toast.type" :border="toast.border" :value="toast.value"
          outlined prominent text dismissible></Toast>
        <Heading tag="h5" class="headingClass">Chips </Heading>
        <span class="inlineClass">
          <Chips v-for="chip in chipsItem" :key="chip.id" :id="chip.id" :color="chip.color" :icon="chip.icon" close :text="chip.text" @close="closeChip" />
        </span>
        <v-row>
          <v-col class="col-4">
            <Heading tag="h5" class="headingClass">Toggle</Heading>
            <Toggle v-for="el in ['Toggle 1', 'Toggle 2']" :key="el" :label="el" row />
          </v-col>
          <v-col class="col-4">
            <Heading tag="h5" class="headingClass">Radio Button</Heading>
            <RadioButton :data="radioGroup" row />
          </v-col>
          <v-col class="col-4">
            <Heading tag="h5" class="headingClass">CheckBox</Heading>
            <CheckBox v-for="el in ['checkbox 1', 'checkbox 2', 'checkbox 3']" :key="el" :label="el" row />
          </v-col>
        </v-row>


      </v-col>
    </v-row>
  </v-container>
</template>                         

<script>
import Heading from '@/components/UIComponents/Heading.vue';
import InputField from '@/components/UIComponents/InputField.vue';
import DropDown from '@/components/UIComponents/DropDown.vue';
import DatePicker from '@/components/UIComponents/DatePicker.vue';
import Chips from '@/components/UIComponents/Chips.vue';
import Toast from '@/components/UIComponents/Toast.vue';
import RadioButton from '@/components/UIComponents/RadioButton.vue';
import CheckBox from '@/components/UIComponents/CheckBox.vue';
import Toggle from '@/components/UIComponents/Toggle.vue';
export default {
  name: 'UIDashboard',
  components: {
    Heading,
    InputField,
    DropDown,
    DatePicker,
    Chips,
    Toast,
    RadioButton,
    CheckBox,
    Toggle
  },
  data: () => ({
    date: '',
    radioGroup: [
      {
        id: 1,
        label: 'Male',
        value: 'male'
      },
      {
        id: 2,
        label: 'FeMale',
        value: 'female'
      },
      {
        id: 3,
        label: 'Other',
        value: 'other'
      },
    ],
    toastItems: [
      {
        id: 1,
        icon: '$mdiAccount',
        value: 'You successfully upload file!',
        type: 'success',
        border: 'top'
      },
      {
        id: 2,
        icon: '$mdiAccount',
        value: 'There was an error loding your file...',
        type: 'warning',
        border: 'bottom'
      },
      {
        id: 3,
        icon: '$mdiAccount',
        value: 'Problem with upload file.',
        type: 'error',
        border: 'bottom'
      }
    ],
    chipsItem: [
      {
        id: 1,
        icon: 'mdi-delete',
        color: 'blue',
        text: 'item 1',
        isDark: true
      },
      {
        id: 2,
        icon: 'mdi-earth',
        color: 'blue',
        text: 'item 2',
        isDark: false
      },
      {
        id: 3,
        icon: 'mdi-earth',
        color: 'green',
        text: 'item 3',
        isDark: false
      },
      {
        id: 4,
        icon: 'mdi-close',
        color: 'blue',
        text: 'item 4',
        isDark: true
      }
    ],
    items: [
      {
        id: 1,
        name: 'item 1'
      },
      {
        id: 2,
        name: 'item 3'
      },
      {
        id: 3,
        name: 'item 3'
      }
      , {
        id: 4,
        name: 'item 4'
      },
      {
        id: 5,
        name: 'item 5'
      }
    ],
    inputs: [
      {
        id: 1,
        label: 'Input Field',
        type: 'text',
        placeholder: 'Input Placeholder',
        value: '',
        rules: [],
        prependicon: "",
        appendicon: "",
        isDisable: false,
        hint: 'Enter something to test'
      },
      {
        id: 2,
        label: 'Input Field Focus',
        type: 'text',
        value: '',
        rules: [],
        isDisable: false,
        prependicon: "",
        appendicon: "",
        placeholder: 'Input Placeholder',
        hint: 'Enter something to test'
      },
      {
        id: 3,
        label: 'Input Field Disabled',
        type: 'text',
        value: '',
        isDisable: true,
        rules: [],
        prependicon: "",
        appendicon: "",
        placeholder: 'Input Placeholder',
        hint: 'Enter something to test'
      },
      {
        id: 4,
        label: 'Input Field Error',
        type: 'text',
        value: '',
        placeholder: 'Input Placeholder',
        rules: [
          value => !!value || 'Value is required',
        ],
        prependicon: "",
        appendicon: "",
        isDisable: false,
        hint: 'Enter something to test'
      },
      {
        id: 5,
        label: 'Custom Input Field',
        type: 'text',
        value: '',
        prependicon: "mdi-currency-usd",
        appendicon: "",
        placeholder: 'Input Placeholder',
        rules: [
          value => !!value || 'Value is required',
        ],
        isDisable: false,
        hint: 'Enter something to test'
      },
      {
        id: 6,
        label: 'Custom Input Field',
        type: 'text',
        value: '',
        prependicon: "",
        appendicon: "mdi-percent",
        placeholder: 'Input Placeholder',
        rules: [
          value => !!value || 'Value is required',
        ],
        isDisable: false,
        hint: 'Enter something to test'
      },

      {
        id: 7,
        label: 'Input Field Number',
        type: 'Number',
        value: '',
        placeholder: 'Input Placeholder',
        rules: [],
        prependicon: "",
        appendicon: "",
        isDisable: false,
        hint: 'Enter something to test'
      },
      {
        id: 8,
        label: 'Text Area',
        type: 'textarea',
        value: '',
        placeholder: 'Input Placeholder',
        rules: [],
        prependicon: "",
        appendicon: "",
        isDisable: false,
        hint: 'Enter something to test'
      }
    ]
  }),
  methods: {
    closeChip(id) {
      try {
        this.chipsItem = this.chipsItem.filter(el => el.id !== id)
      } catch(err) {
        console.log(err)
      }
    }
  }
}
</script>
