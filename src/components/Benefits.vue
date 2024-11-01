<script setup lang="ts">
import { Card, CardContent, CardHeader, CardTitle } from "@/components/ui/card";
import { useColorMode } from "@vueuse/core";
const mode = useColorMode();

import {
  Sparkle,
  Tag,
  Paintbrush,
  Blocks,
  LineChart,
  Wallet,
} from "lucide-vue-next";

interface BenefitsProps {
  icon: string;
  title: string;
  description: string;
}

const benefitList: BenefitsProps[] = [
  {
    icon: "blocks",
    title: "Expertise in Web Development",
    description:
      "Kami sudah berpengalaman lebih dari 10 tahun dalam bidang Web Development.",
  },
  {
    icon: "lineChart",
    title: "Cutting-Edge Technologies",
    description:
      "Kami selalu mengikuti perkembangan teknologi terbaru dalam industri.",
  },
  {
    icon: "wallet",
    title: "Client-Centric Approach",
    description:
      "Kami pastikan produk yang kami tawarkan benar-benar memenuhi ekspektasi Anda.",
  },
  {
    icon: "sparkle",
    title: "Transparent and Reliable",
    description:
      "Mulai dari awal pengerjaan proyek kami akan selalu melibatkan Anda.",
  },
];

const iconMap: Record<
  string,
  | typeof Sparkle
  | typeof Tag
  | typeof Paintbrush
  | typeof Blocks
  | typeof LineChart
  | typeof Wallet
> = {
  sparkle: Sparkle,
  tag: Tag,
  paintbrush: Paintbrush,
  blocks: Blocks,
  lineChart: LineChart,
  wallet: Wallet,
};
</script>

<template>
  <section id="benefits" class="container py-24 sm:py-32">
    <div class="grid lg:grid-cols-2 place-items-center lg:gap-24">
      <div>
        <h2 class="text-3xl md:text-4xl font-bold mb-4">
          We Are Professional
        </h2>
        <p class="text-xl text-muted-foreground mb-8">
          Kami adalah tim yang ahli di bidang pengembangan perangkat lunak. 
          Di sini, kami ingin berbagi lebih banyak tentang siapa kami dan keahlian kami dalam menciptakan solusi perangkat lunak yang profesional.
        </p>
      </div>

      <div class="grid lg:grid-cols-2 gap-4 w-full">
        <Card
          v-for="({ icon, title, description }, index) in benefitList"
          :key="title"
          class="bg-muted/50 dark:bg-card hover:bg-background dark:hover:bg-background transition-all delay-75 group/number"
        >
          <CardHeader>
            <div class="flex justify-between">
              <component
                :is="iconMap[icon]"
                class="size-8 mb-6 text-primary"
              />

              <span
                class="text-5xl text-muted-foreground/15 font-medium transition-all delay-75 group-hover/number:text-muted-foreground/30"
              >0{{ index + 1 }}</span>
            </div>

            <CardTitle>{{ title }}</CardTitle>
          </CardHeader>

          <CardContent class="text-muted-foreground">
            {{ description }}
          </CardContent>
        </Card>
      </div>
    </div>
    <div class="relative group mt-14">
      <!-- gradient shadow -->
      <div
        class="absolute -top-6 right-12 w-[90%] h-12 lg:h-[80%] bg-primary/50 blur-3xl rounded-full img-shadow-animation"
      ></div>

      <img
        class="w-full md:w-[1200px] mx-auto rounded-lg relative rouded-lg leading-none flex items-center border border-t-2 border-t-primary/30 img-border-animation"
        :src="mode === 'light' ? '20241101_021538_0000.png' : '20241101_021538_0000.png'"
        alt="dashboard using shadcn-vue"
      />

      <!-- gradient effect img -->
      <div
        class="absolute bottom-0 left-0 w-full h-20 md:h-28 bg-gradient-to-b from-background/0 via-background/50 to-background rounded-lg"
      ></div>
    </div>
  </section>
</template>
