<template>
  <div v-if="NguyenCK21V7K024" class="page">
    <h4>Tạo mới Liên hệ</h4>
    <ContactForm
      :contact="contact"
      @submit:contact="SubmitContact"
    />
    
  </div>
  <p>{{ message }}</p>
</template>
<script>
import ContactForm from "@/components/ContactForm.vue";
import ContactService from "@/services/contact.service";
export default {
  components: {
    ContactForm,
  },
  data() {
    return {
      NguyenCK21V7K024: true,
      contact: {},
      message: ""
    };
  },
  methods: {
    
    async SubmitContact(data) {
      try {
        await ContactService.create(data);
        this.message = "Liên hệ được thêm thành công.";
        this.NguyenCK21V7K024 = false;
      } catch (error) {
        console.log(error);
      }
    },
   
  },
};
</script>
