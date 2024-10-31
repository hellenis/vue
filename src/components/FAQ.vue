<script setup lang="ts">
import {
  Accordion,
  AccordionContent,
  AccordionItem,
  AccordionTrigger,
} from "@/components/ui/accordion";

interface FAQProps {
  question: string;
  answer: string;
  value: string;
}

const FAQList: FAQProps[] = [
  {
    question: "Bagaimana langkah pertama yang harus saya lakukan jika tertarik untuk bekerja sama?",
    answer: "Langkah pertama adalah menghubungi kami melalui email atau formulir kontak di situs web kami. Kami akan mengatur pertemuan awal untuk mendiskusikan kebutuhan dan tujuan proyek Anda.",
    value: "item-1",
  },
  {
    question: "Apakah ada dukungan jika terjadi masalah pada sistem yang sudah selesai dibuat?",
    answer:
      "Ya, kami menyediakan dukungan pasca-proyek untuk memastikan sistem berjalan dengan lancar. Tim dukungan kami siap membantu jika terjadi masalah atau jika Anda memerlukan pembaruan.",
    value: "item-2",
  },
  {
    question:
      "Apakah saya dapat meminta revisi atau perbaikan jika ada yang kurang memuaskan?",
    answer:
      "Tentu saja, kami memahami bahwa revisi mungkin diperlukan. Kami menawarkan beberapa kali revisi dalam kontrak proyek untuk memastikan hasil akhirnya sesuai dengan harapan Anda.",
    value: "item-3",
  },
  {
    question: "Berapa budget yang harus disiapkan untuk mengembangkan sebuah proyek?",
    answer: "Budget tergantung pada kompleksitas dan cakupan proyek. Setelah pertemuan awal, kami akan memberikan perkiraan biaya yang lebih akurat berdasarkan kebutuhan spesifik Anda.",
    value: "item-4",
  },
  {
    question:
      "Mengapa perlu menggunakan jasa pengembangan perangkat lunak profesional?",
    answer: "Menggunakan jasa pengembangan perangkat lunak profesional memastikan bahwa Anda mendapatkan solusi yang optimal dan terukur. Tim profesional memiliki keahlian dan pengalaman untuk mengatasi tantangan teknis dan menghasilkan produk berkualitas tinggi.",
    value: "item-5",
  },
];
</script>

<template>
  <section
    id="faq"
    class="container md:w-[700px] py-24 sm:py-32"
  >
    <div class="text-center mb-8">
      <h2 class="text-lg text-primary text-center mb-2 tracking-wider">Pertanyaan Seputar T!CKK</h2>

      <h2 class="text-3xl md:text-4xl text-center font-bold">
        Di bawah ini adalah beberapa pertanyaan yang sering diajukan oleh calon klien kami, mungkin termasuk Anda.
      </h2>
    </div>

    <Accordion
      type="single"
      collapsible
      class="AccordionRoot"
    >
      <AccordionItem
        v-for="{ question, answer, value } in FAQList"
        :key="value"
        :value="value"
      >
        <AccordionTrigger class="text-left"> {{ question }} </AccordionTrigger>

        <AccordionContent>{{ answer }}</AccordionContent>
      </AccordionItem>
    </Accordion>

    <h3 class="font-medium mt-4">
      Still have questions?
      <a
        href="#"
        class="text-muted-foreground"
      >
        <a
          href="#"
          class="underline"
          >Contact us</a
        >
      </a>
    </h3>
  </section>
</template>
