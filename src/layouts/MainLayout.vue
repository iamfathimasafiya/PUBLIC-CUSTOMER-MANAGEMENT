<template>
  <q-layout view="lHh Lpr lff" class="bg-dark text-white">
    <q-header elevated class="bg-black text-white q-py-sm">
      <q-toolbar class="container q-px-lg">
        <q-btn flat no-caps no-wrap dense class="q-mr-sm" to="/">
          <div class="row items-center">
            <div class="logo-box q-mr-sm">
              <q-icon name="hub" size="32px" color="secondary" />
            </div>
            <div class="text-h5 text-weight-bolder tracking-tighter">
              CUSTO<span class="text-secondary">MAX</span>
            </div>
          </div>
        </q-btn>

        <q-space />

        <div class="gt-sm row items-center q-gutter-lg">
          <q-btn flat label="Home" to="/" class="nav-link" />
          <q-btn flat label="Features" href="#features" class="nav-link" />
          <q-btn flat label="Analytics" href="#analytics" class="nav-link" />
          <q-btn flat label="Contact" href="#contact" class="nav-link" />

          <q-btn
            unelevated
            color="secondary"
            text-color="white"
            label="Try for Free"
            class="q-px-lg q-py-sm rounded-borders text-weight-bold shadow-10"
          />
        </div>

        <q-btn dense flat round icon="menu" class="lt-md" @click="toggleRightDrawer" />
      </q-toolbar>
    </q-header>

    <q-drawer
      v-model="rightDrawerOpen"
      side="right"
      overlay
      behavior="mobile"
      class="bg-black text-white"
    >
      <q-list padding class="q-mt-xl">
        <q-item clickable v-ripple to="/" class="text-white q-py-md">
          <q-item-section avatar>
            <q-icon name="home" color="secondary" />
          </q-item-section>
          <q-item-section class="text-h6">Home</q-item-section>
        </q-item>

        <q-item clickable v-ripple href="#features" class="text-white q-py-md">
          <q-item-section avatar>
            <q-icon name="widgets" color="secondary" />
          </q-item-section>
          <q-item-section class="text-h6">Features</q-item-section>
        </q-item>

        <q-item clickable v-ripple href="#analytics" class="text-white q-py-md">
          <q-item-section avatar>
            <q-icon name="insights" color="secondary" />
          </q-item-section>
          <q-item-section class="text-h6">Analytics</q-item-section>
        </q-item>

        <q-item clickable v-ripple href="#contact" class="text-white q-py-md">
          <q-item-section avatar>
            <q-icon name="mail" color="secondary" />
          </q-item-section>
          <q-item-section class="text-h6">Contact</q-item-section>
        </q-item>

        <q-separator dark class="q-my-lg" />

        <div class="q-px-md">
          <q-btn
            unelevated
            color="secondary"
            text-color="white"
            label="Try for Free"
            class="full-width q-py-md rounded-borders text-weight-bold"
          />
        </div>
      </q-list>
    </q-drawer>

    <q-page-container>
      <router-view />
    </q-page-container>

    <q-footer class="bg-black text-white q-py-xl" style="border-top: 2px solid #e53935">
      <div class="container">
        <div class="row q-col-gutter-xl">
          <div class="col-12 col-md-4">
            <div class="text-h5 text-weight-bolder q-mb-md">
              CUSTO<span class="text-secondary">MAX</span>
            </div>
            <p class="text-grey-5 q-mb-lg" style="max-width: 300px">
              The ultimate customer management solution for modern enterprises. Scalable, secure,
              and data-driven.
            </p>
            <div class="row q-gutter-md">
              <q-btn flat round color="grey-5" icon="facebook" size="sm" />
              <q-btn flat round color="grey-5" icon="twitter" size="sm" />
              <q-btn flat round color="grey-5" icon="linkedin" size="sm" />
            </div>
          </div>
          <div class="col-6 col-md-2">
            <div class="text-weight-bold q-mb-md">Company</div>
            <q-list dense flat>
              <q-item clickable class="q-px-none text-grey-5">About Us</q-item>
              <q-item clickable class="q-px-none text-grey-5">Careers</q-item>
              <q-item clickable class="q-px-none text-grey-5">Contact</q-item>
            </q-list>
          </div>
          <div class="col-6 col-md-2">
            <div class="text-weight-bold q-mb-md">Product</div>
            <q-list dense flat>
              <q-item clickable class="q-px-none text-grey-5">Features</q-item>
              <q-item clickable class="q-px-none text-grey-5">Security</q-item>
              <q-item clickable class="q-px-none text-grey-5">Pricing</q-item>
            </q-list>
          </div>
          <div class="col-12 col-md-4">
            <div class="text-weight-bold q-mb-md">Subscribe</div>
            <q-input
              dark
              standout
              dense
              v-model="email"
              placeholder="Email address"
              class="q-mb-md"
            >
              <template v-slot:append>
                <q-btn flat round color="secondary" icon="send" />
              </template>
            </q-input>
            <p class="text-caption text-grey-7">Stay updated with our latest releases.</p>
          </div>
        </div>
        <q-separator dark class="q-my-xl" style="opacity: 0.1" />
        <div class="row justify-between items-center text-grey-7">
          <div>&copy; 2024 CUSTOMAX. All rights reserved.</div>
          <div class="row q-gutter-md">
            <span>Privacy Policy</span>
            <span>Terms of Service</span>
          </div>
        </div>
      </div>
    </q-footer>
  </q-layout>
</template>

<script setup>
import { ref } from 'vue'

const rightDrawerOpen = ref(false)
const email = ref('')

function toggleRightDrawer() {
  rightDrawerOpen.value = !rightDrawerOpen.value
}
</script>

<style lang="scss">
.container {
  max-width: 1200px;
  margin: 0 auto;
}

.tracking-tighter {
  letter-spacing: -1px;
}

.nav-link {
  font-weight: 500;
  transition: all 0.3s ease;
  &:hover {
    color: $secondary !important;
  }
}

.logo-box {
  background: rgba($secondary, 0.1);
  padding: 4px;
  border-radius: 8px;
  border: 1px solid rgba($secondary, 0.2);
}

.border-top-secondary {
  border-top: 2px solid $secondary;
}

// Global styles for the dark theme
body.body--dark {
  background: $dark-page;
}
</style>
