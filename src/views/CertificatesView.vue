<script>
export default {
  data() {
    return {
      certificates: [
        {
          id: 1,
          name: '3rd Place — IDEAFEST 2025',
          description: 'Third-place team award in the Digitalization of Shipping & Logistics Business Competition, held by PT SPIL and Universitas Ciputra.',
          image: 'sertif-spil.jpg'
        },
        {
          id: 2,
          name: 'PTMB 2025 Committee',
          description: 'Creative Media division, Faculty of Computer Science student orientation.',
          image: 'sertif-panitia-ptmb.jpg'
        },
        {
          id: 3,
          name: 'LKTD 2026 Committee',
          description: 'Accommodation division, Faculty of Computer Science leadership training.',
          image: 'sertif-panit-lktd.jpg'
        },
        {
          id: 4,
          name: 'HMTI Committee 2024/2025',
          description: 'Recognition for serving in the Informatics Engineering Student Association.',
          image: 'sertif-hmti1.jpg'
        },
        {
          id: 5,
          name: 'Apple Developer Academy Seminar',
          description: 'Certificate of participation in a seminar hosted with Apple Developer Academy.',
          image: 'sertif-apple.jpg'
        },
        {
          id: 6,
          name: 'PPK ORMAWA 2025/2026',
          description: 'Certificate of participation in the Student Organization Capacity Building Program.',
          image: 'ppk-ormawa.jpg'
        },
        {
          id: 7,
          name: 'JAKA APTIK REGIO BARAT 2026 Committee',
          description: 'Creative Media division, national Catholic student character development training.',
          image: 'sertif-aptik.png'
        }
      ]
    };
  }
}
</script>

<template>
  <div class="px-5 py-5 md:px-12 md:py-10 text-left text-sky-50 mx-3">
    <article>
      <header>
        <div class="text-2xl font-bold text-white mb-10 fadein-bot title-section flex items-center justify-center flex-col">
          <h1>My Journey</h1>
          <p class="text-base font-normal text-transparent bg-clip-text bg-gradient-to-r from-slate-100 to-ice-blue">
            Certificates and achievements along the way
          </p>
        </div>
      </header>

      <section>
        <div class="grid grid-cols-1 gap-4 pb-32 md:grid-cols-3 md:gap-3 xl:grid-cols-3 xl:gap-3 2xl:gap-5 fade-zoom-in">
          <article v-for="certificate in certificates" :key="certificate.id">
            <div class="certificate-card flex h-full flex-col items-center gap-3 rounded-xl border border-[#383838] bg-[#1e1e1f] px-5 py-5 text-sky-50 hover:bg-[#282828]">
              <a
                class="block w-full overflow-hidden rounded-xl bg-[#141414] focus:outline-none focus-visible:ring-2 focus-visible:ring-ice-blue"
                :href="'/certificates/' + certificate.image"
                target="_blank"
                rel="noreferrer"
                :aria-label="'Open certificate: ' + certificate.name">
                <img
                  class="aspect-[4/3] h-full w-full object-contain"
                  :src="'/certificates/' + certificate.image"
                  :alt="certificate.name"
                  loading="lazy">
              </a>
              <div class="w-full text-left">
                <h2 class="font-medium text-white">{{ certificate.name }}</h2>
                <p class="mt-2 text-xs text-[#c1c1c1] md:text-sm">{{ certificate.description }}</p>
              </div>
            </div>
          </article>
        </div>
      </section>
    </article>
  </div>
</template>

<style>
.certificate-card {
  transition: transform 0.3s ease;
}

.certificate-card:hover {
  transform: translateY(-8px);
}

@keyframes fadeZoomIn {
  0% {
    opacity: 0;
    transform: scale(0.5);
  }
  100% {
    opacity: 1;
    transform: scale(1);
  }
}

.fade-zoom-in {
  animation: fadeZoomIn 1s ease-in-out;
}
</style>
