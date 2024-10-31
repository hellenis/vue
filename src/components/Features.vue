<script setup lang="ts">
import { Card, CardContent, CardHeader, CardTitle } from "@/components/ui/card";

import {
  Paintbrush,
  MessageCircle,
  TabletSmartphone,
  BadgeCheck,
  Goal,
  PictureInPicture,
  MousePointerClick,
  Newspaper,
} from "lucide-vue-next";

interface FeaturesProps {
  icon: string;
  title: string;
  description: string;
}

const featureList: FeaturesProps[] = [
  {
    icon: "tabletSmartphone",
    title: "Mobile Development",
    description:
      "Mendevelop aplikasi mobile, baik IOS maupun Android. Mulai dari pengembangan hingga optimisasi kinerja.",
  },
  {
    icon: "badgeCheck",
    title: "Web Development",
    description:
      "Kami menyediakan jasa pembuatan website, seperti company profile, redesign website dan kustomisasi website.",
  },
  {
    icon: "goal",
    title: "Product Design",
    description:
      "Kami menyediakan desain produk yang inovatif dan menarik, mulai dari penelitian pengguna hingga pembuatan prototipe.",
  },
  {
    icon: "pictureInPicture",
    title: "Konsultan ISO 27001",
    description:
      "Percayakan pada kami! Dapatkan solusi lengkap implementasi dan sertifikasi ISO 27001. Lindungi data perusahaan Anda dengan standar internasional.",
  },
  {
    icon: "mousePointerClick",
    title: "IT Consultant",
    description:
      "Konsultasi IT untuk meningkatkan strategi teknologi perusahaan. Evaluasi, Perencanaan Infrastuktur dan Implementasi.",
  },
  {
    icon: "newspaper",
    title: "IT Auditor",
    description:
      "Membantu pemeriksaan dan mengavaluasi sistem teknologi informasi (TI) suatu organisasi agar sistem Anda berjalan dengan efisien, aman dan sesuai dengan standar yang telah ditetapkan.",
  },
    {
    icon: "newspaper",
    title: "Integrated System",
    description:
      "Membantu mengintergrasi sistem Anda. Termasuk keamanan, otomatisasi dan pemantauan real-time.",
  },
    {
    icon: "newspaper",
    title: "ERP",
    description:
      "Kami menyediakan solusi ERP untuk mengintegrasikan dan mengelola proses bisnis secara efisien dalam perusahaan Anda.",
  },
];

const iconMap: Record<
  string,
  | typeof TabletSmartphone
  | typeof BadgeCheck
  | typeof Goal
  | typeof PictureInPicture
  | typeof Paintbrush
  | typeof MousePointerClick
  | typeof MessageCircle
  | typeof Newspaper
> = {
  tabletSmartphone: TabletSmartphone,
  badgeCheck: BadgeCheck,
  goal: Goal,
  pictureInPicture: PictureInPicture,
  paintbrush: Paintbrush,
  mousePointerClick: MousePointerClick,
  messageCircle: MessageCircle,
  newspaper: Newspaper,
};
</script>

<template>
  <section
    id="features"
    class="container py-24 sm:py-32"
  >

    <h2 class="text-3xl md:text-4xl text-center font-bold mb-4">
      Layanan Kami
    </h2>

    <h3 class="md:w-1/2 mx-auto text-xl text-center text-muted-foreground mb-8">
      Temukan solusi terbaik untuk bisnis Anda dengan bantuan tim profesional kami yang berpengalaman di berbagai bidang, termasuk pengembangan web, pengembangan mobile, desain produk dan konsultasi IT.
    </h3>

    <div class="grid sm:grid-cols-2 lg:grid-cols-3 gap-4">
      <div
        v-for="{ icon, title, description } in featureList"
        :key="title"
      >
        <Card class="h-full bg-background border-0 shadow-none">
          <CardHeader class="flex justify-center items-center">
            <div
              class="bg-primary/20 p-2 rounded-full ring-8 ring-primary/10 mb-4"
            >
              <component
                :is="iconMap[icon]"
                class="size-6 text-primary"
              />
            </div>

            <CardTitle>
              {{ title }}
            </CardTitle>
          </CardHeader>

          <CardContent class="text-muted-foreground text-center">
            {{ description }}
          </CardContent>
        </Card>
      </div>
    </div>
  </section>
</template>

<style lang="less" scoped></style>
