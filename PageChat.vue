<template>
  <q-page class="flex column">
        <q-banner class="bg-grey-4 text-center">
     User is Offline
     
    </q-banner>
      <div class="q-pa-md column col justify-end">
             <q-chat-message  
        v-for= "message in messages" 
        :key="message.text"    
        :name="message.from"
        :text="[message.text]"
        :sent="message.from == 'me' ? true : false"
      />
      
      </div>
      <q-footer elevated>
        <q-toolbar>
        <q-form @click= "sendMessage" class="full-width"> 
            <q-input bg-color= "white" outlined rounded v-model= "newMessage" label="Message" dense class="full-width"> 
      

    

        
        <template v-slot:after>
          <q-btn round dense flat type= "submit" icon="send" color="white" />
        </template>
      </q-input>
            
            </q-form>  
      
        </q-toolbar>
      </q-footer>

  </q-page>
</template>

<script>
export default {
  data() {
      return {
          newMessage: '',
          messages: [

              {
                  text: 'Hello Sonali! How Are You?',
                  from: 'me'
              },
               {
                  text: 'Good dear How are you?',
                  from: 'me'
              },
               {
                  text: 'great,Thanks',
                  from: 'them'
              }
          ]
      }
  },
    methods: {
      sendMessage() {
          this.messages.push({
              text: this.newMessage,
              from: 'me'
          })
      }
  }
}
</script>
<style>

</style>