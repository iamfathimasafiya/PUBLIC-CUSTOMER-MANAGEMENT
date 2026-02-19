<template>
  <q-page class="index-page">
    <!-- Hero Section -->
    <section class="hero-section relative-position overflow-hidden">
      <div class="hero-dots"></div>
      <div class="container q-px-lg q-py-xl row items-center">
        <div class="col-12 col-md-6 q-pr-md-xl text-center text-md-left">
          <div class="badge-new q-mb-md inline-block">
            <span class="text-secondary text-weight-bold">NEW</span> AI-Powered Insights are here
          </div>
          <h1 class="text-h1 text-weight-bolder line-height-tight q-mb-md">
            Revolutionize Your <br />
            <span class="text-gradient">Customer Relations</span>
          </h1>
          <p class="text-h6 text-grey-5 q-mb-xl weight-400 max-width-p mx-auto-sm">
            The all-in-one platform to track, engage, and grow your customer base with
            high-precision analytics and automated workflows.
          </p>
          <div class="row q-gutter-md justify-center justify-md-start">
            <q-btn
              unelevated
              color="secondary"
              label="Get Started Now"
              class="q-px-xl q-py-md text-weight-bold rounded-lg shadow-20 hover-scale"
            />
            <q-btn
              outline
              color="white"
              label="Watch Demo"
              icon="play_circle"
              class="q-px-xl q-py-md text-weight-bold rounded-lg hover-bg-white"
            />
          </div>
        </div>
        <div class="col-12 col-md-6 q-mt-xl q-mt-md-none relative-position">
          <div class="hero-image-container">
            <div class="glass-card main-dashboard flex flex-center">
              <div class="text-center">
                <q-icon name="dashboard" size="100px" color="secondary" style="opacity: 0.2" />
                <div class="text-grey-7 q-mt-sm">Interactive Dashboard Preview</div>
              </div>
            </div>
            <div class="glass-card stat-card-1 q-pa-md">
              <div class="row items-center q-gutter-sm">
                <q-avatar color="secondary" text-color="white" size="32px" icon="person_add" />
                <div>
                  <div class="text-caption text-grey-5">New Leads</div>
                  <div class="text-weight-bolder">+142%</div>
                </div>
              </div>
            </div>
            <div class="glass-card stat-card-2 q-pa-md">
              <div class="row items-center q-gutter-sm">
                <q-avatar color="light-green-7" text-color="white" size="32px" icon="trending_up" />
                <div>
                  <div class="text-caption text-grey-5">Revenue</div>
                  <div class="text-weight-bolder">$84,200</div>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- Stats Section -->
    <section class="stats-section q-py-xl">
      <div class="container q-px-lg">
        <div class="row q-col-gutter-lg justify-center">
          <div v-for="(stat, index) in stats" :key="index" class="col-6 col-sm-3 text-center">
            <div class="text-h3 text-weight-bolder text-secondary">{{ stat.value }}</div>
            <div class="text-subtitle1 text-grey-5 q-mt-xs">{{ stat.label }}</div>
          </div>
        </div>
      </div>
    </section>

    <!-- Features Section -->
    <section id="features" class="features-section q-py-max">
      <div class="container q-px-lg">
        <div class="text-center q-mb-xl">
          <div class="text-secondary text-weight-bold q-mb-sm">CORE FEATURES</div>
          <h2 class="text-h2 text-weight-bolder q-mb-md">Built for Modern Businesses</h2>
          <p class="text-grey-5 max-width-600 mx-auto">
            Everything you need to manage your customer lifecycle in one unified interface.
          </p>
        </div>
        <div class="row q-col-gutter-xl">
          <div v-for="(feature, index) in features" :key="index" class="col-12 col-md-4">
            <div class="feature-card q-pa-xl full-height">
              <div class="icon-box q-mb-lg">
                <q-icon :name="feature.icon" size="32px" color="secondary" />
              </div>
              <h3 class="text-h5 text-weight-bold q-mb-md">{{ feature.title }}</h3>
              <p class="text-grey-5 line-height-relaxed">{{ feature.desc }}</p>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- Analytics Highilght (Dark/Contrast) -->
    <section id="analytics" class="analytics-highlight q-py-max bg-black">
      <div class="container q-px-lg">
        <div class="row items-center q-col-gutter-xl">
          <div class="col-12 col-md-6">
            <div class="analytics-preview">
              <div class="glass-card q-pa-lg">
                <div class="row justify-between items-center q-mb-md">
                  <div class="text-weight-bold">Retention Growth</div>
                  <q-icon name="more_vert" color="grey-7" />
                </div>
                <div class="chart-mockup">
                  <div class="bar-container" v-for="n in 7" :key="n">
                    <div class="bar" :style="{ height: 20 + Math.random() * 60 + '%' }"></div>
                  </div>
                </div>
              </div>
            </div>
          </div>
          <div class="col-12 col-md-6">
            <h2 class="text-h2 text-weight-bolder q-mb-md">Data Driven Decisions</h2>
            <p class="text-grey-5 q-mb-xl text-h6 weight-400">
              Stop guessing. Our advanced analytics engine provides real-time insights into customer
              behavior, churn prediction, and lifetime value.
            </p>
            <q-list padding>
              <q-item v-for="(item, index) in analyticsList" :key="index" class="q-px-none q-mb-md">
                <q-item-section avatar>
                  <q-icon name="check_circle" color="secondary" />
                </q-item-section>
                <q-item-section>
                  <div class="text-weight-bold text-h6">{{ item.title }}</div>
                  <div class="text-grey-5">{{ item.desc }}</div>
                </q-item-section>
              </q-item>
            </q-list>
          </div>
        </div>
      </div>
    </section>

    <!-- Call to Action -->
    <section id="contact" class="cta-section q-py-max">
      <div class="container q-px-lg">
        <div class="glass-card cta-box q-pa-xl text-center relative-position overflow-hidden">
          <div class="cta-glow"></div>
          <div class="relative-position z-index-1">
            <h2 class="text-h2 text-weight-bolder q-mb-md">Ready to scale your business?</h2>
            <p class="text-h6 text-grey-5 q-mb-xl max-width-600 mx-auto">
              Join over 5,000+ companies growing their revenue with CUSTO<span
                class="text-secondary text-weight-bold"
                >MAX</span
              >.
            </p>
            <div class="row q-gutter-md justify-center">
              <q-btn
                unelevated
                color="secondary"
                label="Start 14-Day Free Trial"
                class="q-px-xl q-py-md text-weight-bold rounded-lg shadow-20"
              />
              <q-btn
                outline
                color="white"
                label="Contact Sales"
                class="q-px-xl q-py-md text-weight-bold rounded-lg"
              />
            </div>
          </div>
        </div>
      </div>
    </section>
  </q-page>
</template>

<script setup>
const stats = [
  { value: '500K+', label: 'Customers Managed' },
  { value: '98%', label: 'Retention Rate' },
  { value: '24/7', label: 'Priority Support' },
  { value: '4.9/5', label: 'User Rating' },
]

const features = [
  {
    title: 'Smart Contact Management',
    desc: 'Organize and segment your customer base with intelligent tagging and automated data enrichment.',
    icon: 'groups',
  },
  {
    title: 'Omnichannel Engagement',
    desc: 'Connect with customers via Email, SMS, and WhatsApp—all from a single, unified interface.',
    icon: 'dynamic_feed',
  },
  {
    title: 'Sales Pipeline Tracking',
    desc: 'Visual deal boards help you track leads from discovery to closing with drag-and-drop ease.',
    icon: 'query_stats',
  },
]

const analyticsList = [
  {
    title: 'Churn Prediction',
    desc: 'Identify at-risk customers before they leave using AI models.',
  },
  {
    title: 'Customer Lifetime Value',
    desc: 'Accurately forecast future revenue from every segment.',
  },
  {
    title: 'Real-time Alerts',
    desc: 'Get notified immediately when key milestones or issues occur.',
  },
]
</script>

<style lang="scss" scoped>
.index-page {
  overflow-x: hidden;
}

.hero-section {
  min-height: 90vh;
  display: flex;
  align-items: center;
}

.q-py-max {
  padding: 100px 0;
}

.text-gradient {
  background: linear-gradient(90deg, #ffffff, $secondary);
  -webkit-background-clip: text;
  background-clip: text;
  -webkit-text-fill-color: transparent;
}

.weight-400 {
  font-weight: 400;
}

.mx-auto {
  margin-left: auto;
  margin-right: auto;
}

.max-width-p {
  max-width: 500px;
}

.max-width-600 {
  max-width: 600px;
}

.line-height-tight {
  line-height: 1.1;
}

.line-height-relaxed {
  line-height: 1.6;
}

.rounded-lg {
  border-radius: 12px;
}

// Badge
.badge-new {
  background: rgba($secondary, 0.1);
  padding: 8px 16px;
  border-radius: 100px;
  border: 1px solid rgba($secondary, 0.2);
  font-size: 0.85rem;
}

// Hero Interactions
.hero-dots {
  position: absolute;
  top: 0;
  right: 0;
  width: 50%;
  height: 100%;
  background-image: radial-gradient(rgba($secondary, 0.1) 2px, transparent 2px);
  background-size: 30px 30px;
  mask-image: linear-gradient(to left, black, transparent);
  z-index: 0;
}

.hero-image-container {
  padding: 20px;
  perspective: 1000px;
  display: flex;
  justify-content: center;
}

.main-dashboard {
  width: 100%;
  max-width: 500px;
  height: 350px;
  border-radius: 24px;
  border: 1px solid rgba(255, 255, 255, 0.1);
  box-shadow: 0 40px 100px rgba(0, 0, 0, 0.5);
  transform: rotateY(-10deg) rotateX(5deg);
}

.stat-card-1 {
  position: absolute;
  top: 5%;
  left: 0;
  border-radius: 16px;
  border: 1px solid rgba(255, 255, 255, 0.1);
  box-shadow: 0 20px 40px rgba(0, 0, 0, 0.3);
  z-index: 10;
  animation: float 6s ease-in-out infinite;
}

.stat-card-2 {
  position: absolute;
  bottom: 10%;
  right: 5%;
  border-radius: 16px;
  border: 1px solid rgba(255, 255, 255, 0.1);
  box-shadow: 0 20px 40px rgba(0, 0, 0, 0.3);
  z-index: 10;
  animation: float 8s ease-in-out infinite reverse;
}

@keyframes float {
  0%,
  100% {
    transform: translateY(0);
  }
  50% {
    transform: translateY(-15px);
  }
}

// Glassmorphism
.glass-card {
  background: rgba(255, 255, 255, 0.03);
  backdrop-filter: blur(20px);
  -webkit-backdrop-filter: blur(20px);
}

// Feature Cards
.feature-card {
  background: rgba(255, 255, 255, 0.02);
  border: 1px solid rgba(255, 255, 255, 0.05);
  border-radius: 24px;
  transition: all 0.4s cubic-bezier(0.175, 0.885, 0.32, 1.275);
  &:hover {
    background: rgba(255, 255, 255, 0.04);
    border-color: rgba($secondary, 0.3);
    transform: translateY(-10px);
  }
}

.icon-box {
  width: 56px;
  height: 56px;
  background: rgba($secondary, 0.1);
  border-radius: 14px;
  display: flex;
  align-items: center;
  justify-content: center;
}

// Analytics Mockup
.analytics-preview {
  .chart-mockup {
    display: flex;
    align-items: flex-end;
    gap: 10px;
    height: 180px;
    padding: 15px 0;
  }
  .bar-container {
    flex: 1;
    background: rgba(255, 255, 255, 0.02);
    height: 100%;
    border-radius: 6px;
    position: relative;
    overflow: hidden;
  }
  .bar {
    position: absolute;
    bottom: 0;
    width: 100%;
    background: linear-gradient(to top, $secondary, lighten($secondary, 10%));
    border-radius: 6px 6px 0 0;
    transition: height 1s ease;
  }
}

// CTA Box
.cta-box {
  border-radius: 32px;
  border: 1px solid rgba($secondary, 0.2);
}

.cta-glow {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  width: 120%;
  height: 120%;
  background: radial-gradient(circle, rgba($secondary, 0.05) 0%, transparent 70%);
  z-index: 0;
}

.z-index-1 {
  position: relative;
  z-index: 1;
}

.hover-scale {
  transition: transform 0.3s ease;
  &:hover {
    transform: scale(1.05);
  }
}

.hover-bg-white:hover {
  background: rgba(255, 255, 255, 0.1) !important;
}

@media (max-width: $breakpoint-sm-max) {
  .text-h1 {
    font-size: clamp(2.5rem, 8vw, 3.5rem);
  }
  .text-h2 {
    font-size: 2.2rem;
  }
  .q-py-max {
    padding: 60px 0;
  }
  .mx-auto-sm {
    margin-left: auto;
    margin-right: auto;
  }
  .hero-section {
    min-height: auto;
    padding: 60px 0;
  }
}

@media (min-width: $breakpoint-md-min) {
  .text-h1 {
    font-size: clamp(3.5rem, 6vw, 4.8rem);
  }
  .text-h2 {
    font-size: 3rem;
  }
}
</style>
