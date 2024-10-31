<script setup lang="ts">
import { Avatar, AvatarFallback, AvatarImage } from "@/components/ui/avatar";

import {
  Card,
  CardContent,
  CardDescription,
  CardHeader,
  CardTitle,
} from "@/components/ui/card";

import {
  Carousel,
  CarouselContent,
  CarouselItem,
  CarouselNext,
  CarouselPrevious,
} from "@/components/ui/carousel";

import { Star } from "lucide-vue-next";

interface ReviewProps {
  image: string;
  name: string;
  userName: string;
  comment: string;
  rating: number;
}

const reviewList: ReviewProps[] = [
  {
    image: "https://github.com/shadcn.png",
    name: "Mustika Regi W",
    userName: "Online shop",
    comment:
      "Kami sangat senang bekerja dengan tim pengembang web T!CKK. Mereka membuat proses pengembangan web terasa begitu lancar dan mudah dipahami.",
    rating: 5.0,
  },
  {
    image: "https://github.com/shadcn.png",
    name: "Sophia Collins",
    userName: "Cybersecurity Analyst",
    comment:
      "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna. ",
    rating: 4.8,
  },

  {
    image: "https://github.com/shadcn.png",
    name: "Laras Riyadi",
    userName: "UMKM",
    comment:
      "T!CKK tidak hanya merancang produk, tetapi juga menciptakan pengalaman yang memikat bagi pengguna akhir. Kami terkesan dengan kreativitas mereka.",
    rating: 4.9,
  },
  {
    image: "https://github.com/shadcn.png",
    name: "Laras Gumarno",
    userName: "Pengusaha",
    comment:
      "Tim T!CKK tidak hanya menciptakan aplikasi mobile yang hebat, tetapi juga mendengarkan kebutuhan dan masukan kami dengan sangat baik.",
    rating: 5.0,
  },
  {
    image: "https://github.com/shadcn.png",
    name: "Ava Mitchell",
    userName: "IT Project Manager",
    comment:
      "Lorem ipsum dolor sit amet, tempor incididunt  aliqua. Ut enim ad minim veniam, quis nostrud incididunt consectetur adipiscing elit.",
    rating: 5.0,
  },
  {
    image: "https://github.com/shadcn.png",
    name: "Adlin Alana",
    userName: "PT Sinarbakti",
    comment:
      "T!CKK berhasil mengintegrasikan sistem- sistem yang berbeda dengan begitu mulusnya, sehingga kami bisa fokus pada hal-hal yang benar-benar penting.",
    rating: 4.9,
  },
];
</script>

<template>
  <section
    id="testimonials"
    class="container py-24 sm:py-32"
  >
    <div class="text-center mb-8">
      <h2 class="text-lg text-primary text-center mb-2 tracking-wider">
        Testimonials
      </h2>

      <h2 class="text-3xl md:text-4xl text-center font-bold mb-4">
        Dengarkan Apa Yang Mereka Katakan
      </h2>
    </div>

    <Carousel
      :opts="{
        align: 'start',
      }"
      class="relative w-[80%] sm:w-[90%] lg:max-w-screen-xl mx-auto"
    >
      <CarouselContent>
        <CarouselItem
          v-for="review in reviewList"
          :key="review.name"
          class="md:basis-1/2 lg:basis-1/3"
        >
          <Card class="bg-muted/50 dark:bg-card">
            <CardContent class="pt-6 pb-0">
              <div class="flex gap-1 pb-6">
                <Star class="size-4 fill-primary text-primary" />
                <Star class="size-4 fill-primary text-primary" />
                <Star class="size-4 fill-primary text-primary" />
                <Star class="size-4 fill-primary text-primary" />
                <Star class="size-4 fill-primary text-primary" />
              </div>

              "{{ review.comment }}"
            </CardContent>

            <CardHeader>
              <div class="flex flex-row items-center gap-4">
                <Avatar>
                  <AvatarImage
                    src="https://www.radix-vue.com/logo.svg"
                    alt="@radix-vue"
                  />
                  <AvatarFallback>SV</AvatarFallback>
                </Avatar>

                <div class="flex flex-col">
                  <CardTitle class="text-lg">{{ review.name }}</CardTitle>
                  <CardDescription>{{ review.userName }}</CardDescription>
                </div>
              </div>
            </CardHeader>
          </Card>
        </CarouselItem>
      </CarouselContent>
      <CarouselPrevious />
      <CarouselNext />
    </Carousel>
  </section>
</template>
