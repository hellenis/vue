<script setup lang="ts">
import { Card, CardContent, CardHeader, CardTitle } from "@/components/ui/card";

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
  <section
    id="benefits"
    class="container py-24 sm:py-32"
  >
    <div class="grid lg:grid-cols-2 place-items-center lg:gap-24">
      <div>


        <h2 class="text-3xl md:text-4xl font-bold mb-4">
          We Are a Profesional
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
                class="size-8 mb-6 text-primary"
                :is="iconMap[icon]"
              />

              <span
                class="text-5xl text-muted-foreground/15 font-medium transition-all delay-75 group-hover/number:text-muted-foreground/30"
                >0{{ index + 1 }}</span
              >
            </div>

            <CardTitle>{{ title }}</CardTitle>
          </CardHeader>

          <CardContent class="text-muted-foreground">
            {{ description }}
          </CardContent>
        </Card>
      </div>
    </div>
  </section>
</template>
