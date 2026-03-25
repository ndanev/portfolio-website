<template>
  <div>
    <section class="section section-contact">
      <div class="container">
        <div class="row justify-content-center mb-5">
          <div class="col-md-6 text-center">
            <h1 class="section-title">
              <span>
                {{ contactContent.sectionTitle }}
              </span>
            </h1>
            <p class="section-lead">
              {{ contactContent.sectionSubtitle }}
            </p>
          </div>
        </div>
        <div class="row">
          <div class="col-md-12">
            <form class="home-form" @submit.prevent="sendMessage">
              <div class="row">
                <div class="col-md-4">
                  <div class="form-group">
                    <label>{{ contactContent.contactLabelTitle }}</label>
                    <input type="text" class="form-control" :placeholder="contactContent.contactPlaceholderTitle">
                  </div>
                </div>
                <div class="col-md-4">
                  <div class="form-group">
                    <label>{{ contactContent.contactLabelName }}</label>
                    <input type="text" class="form-control" :placeholder="contactContent.contactPlaceholderName">
                  </div>
                </div>
                <div class="col-md-4">
                  <div class="form-group">
                    <label>{{ contactContent.contactLabelEmail }}</label>
                    <input type="text" class="form-control" :placeholder="contactContent.contactPlaceholderEmail">
                  </div>
                </div>
              </div>
              <div class="row">
                <div class="col-md-12">
                  <div class="form-colntrol">
                    <label>{{ contactContent.contactLabelMessage }}</label>
                    <textarea class="form-group w-100" rows="10" />
                  </div>
                </div>
              </div>
              <div class="row">
                <div class="col-md-12">
                  <button type="submit" class="button button-primary">
                    {{ contactContent.contactButton }}
                  </button>
                </div>
              </div>
            </form>
          </div>
        </div>
      </div>
    </section>
  </div>
</template>

<script setup>
const contactContent = {
  sectionTitle: 'Contact',
  sectionSubtitle: 'If you have any question or you want to contact us, feel free to send us an email. We’re here to help you!',
  contactLabelTitle: 'Title',
  contactPlaceholderTitle: 'Enter Title',
  contactLabelName: 'Name',
  contactPlaceholderName: 'Enter Name',
  contactLabelEmail: 'Email',
  contactPlaceholderEmail: 'Enter Email',
  contactLabelMessage: 'Message',
  contactButton: 'Send'
}
const sendMessage = () => {
  alert('Coming soon...')
}
</script>