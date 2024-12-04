<script setup>
import { ref } from "vue";

import { Tabs, TabsContent, TabsList, TabsTrigger } from '@/components/ui/tabs';
import { ScrollArea } from '@/components/ui/scroll-area';
import { Button } from "@/components/ui/button";

import OrderInfoIcon from "@/assets/svgs/order-info-icon.svg";
import DriverInfoIcon from "@/assets/svgs/driver-info-icon.svg";
import CustomerInfoIcon from "@/assets/svgs/customer-info-icon.svg";
import CopyTwo from "@/assets/svgs/copy-02.svg";


const selectedVerticalTab = ref("order-info");
const verticalTabValues = [ "order-info", "driver-info", "customer-info" ];
const [ verticalTabValue1, verticalTabValue2, verticalTabValue3 ] = verticalTabValues;
const selectedVerticalTabStyle = "w-full block rounded p-2 mt-4 info";
const notSelectedVerticalTabStyle = "w-full block rounded p-2 mt-4";

const selectVerticalTab = (value) => {
  selectedVerticalTab.value = value;
  console.log(selectedVerticalTab.value);
}
</script>

<template>
  <Tabs 
    :default-value="verticalTabValue1" 
    class="absolute left-4 bottom-4 w-[528px] h-[280px] flex gap-x-4 rounded-lg p-4 bg-white"
    orientation="vertical"
  >

    <TabsList class="w-[159px] block bg-white pr-4 border-r rounded-none">

      <TabsTrigger 
        :value="verticalTabValue1" 
        :class="selectedVerticalTab === verticalTabValue1 ? selectedVerticalTabStyle : notSelectedVerticalTabStyle"
        @click="selectVerticalTab(verticalTabValue1)"
      >
        <div class="flex gap-x-2 items-center">
          <order-info-icon />
          <span class="font-medium text-sm text-[#757575]">
            Order Info
          </span>
        </div>
      </TabsTrigger>

      <TabsTrigger 
        :value="verticalTabValue2" 
        :class="selectedVerticalTab === verticalTabValue2 ? selectedVerticalTabStyle : notSelectedVerticalTabStyle"
        @click="selectVerticalTab(verticalTabValue2)"
      >
        <div class="flex gap-x-2 items-center">
          <driver-info-icon />
          <span class="font-medium text-sm text-[#757575]">
            Driver Info
          </span>
        </div>
      </TabsTrigger>

      <TabsTrigger 
        :value="verticalTabValue3" 
        :class="selectedVerticalTab === verticalTabValue3 ? selectedVerticalTabStyle : notSelectedVerticalTabStyle"
        @click="selectVerticalTab(verticalTabValue3)"
      >
        <div class="flex gap-x-2 items-center">
          <customer-info-icon />
          <span class="font-medium text-sm text-[#757575]">
            Customer Info
          </span>
        </div>
      </TabsTrigger>

    </TabsList>

    <TabsContent 
      value="order-info"
      class="m-0"
    >
      <ScrollArea class="w-[321px] h-[248px]" >

        <section>

          <div class="font-normal text-sm leading-[16.8px] text-[#999999] mb-2">
            Order ID
          </div>

          <span class="font-normal text-sm leading-[16.8px] text-[#101828]">
            #DR3E4478
          </span>

        </section>

        <section class="mt-6">

          <div class="font-normal text-sm leading-[16.8px] text-[#999999] mb-2">
            Pickup address:
          </div>

          <span class="font-normal text-sm leading-[16.8px] text-[#101828]">
            17, Ogunyemi strt, Magodo.
          </span>

        </section>

        <section class="mt-6">

          <div class="font-normal text-sm leading-[16.8px] text-[#999999] mb-2">
            Drop-off address:
          </div>

          <span class="font-normal text-sm leading-[16.8px] text-[#101828]">
            Shop 10/644 GorgerSt, Sydney NSW 2000
          </span>

        </section>

        <section class="mt-6">

          <div class="font-normal text-sm leading-[16.8px] text-[#999999] mb-2">
            Item category:
          </div>

          <span class="font-normal text-sm leading-[16.8px] text-[#101828]">
            Grossery
          </span>

        </section>

        <section class="mt-6">

          <div class="font-normal text-sm leading-[16.8px] text-[#999999] mb-2">
            Weight of items:
          </div>

          <span class="font-normal text-sm leading-[16.8px] text-[#101828]">
            2kg
          </span>

        </section>

        <section class="mt-6">

          <div class="font-normal text-sm leading-[16.8px] text-[#999999] mb-2">
            Weight of items:
          </div>

          <span class="font-normal text-sm leading-[16.8px] text-[#101828]">
            2kg
          </span>

        </section>

        <section class="mt-6">

          <div class="font-normal text-sm leading-[16.8px] text-[#999999] mb-2">
            Drop-Off Notes
          </div>

          <span class="font-normal text-sm leading-[16.8px] text-[#101828]">
            Kindly leave package with the gateman
          </span>

        </section>

      </ScrollArea>
    </TabsContent>

    <TabsContent 
      value="driver-info"
      class="m-0 p-0"
    >
      <ScrollArea class="w-[321px] h-[248px]" >

        <section>

          <span class="font-normal text-sm leading-[16.8px] text-[#999999]">
            Driver’s Name:
          </span>

          <div class="flex gap-x-3 items-center mt-2">
            <img 
              src="../../assets/pngs/baker-avatar.png"
              class="rounded-full border-[0.75px] border-[#000000] border-opacity-[0.08]"
            >
            <span class="font-medium text-sm text-[#101828]">
              Phoenix Baker
            </span>
          </div>

        </section>

        <section class="mt-6">

          <div class="font-normal text-sm leading-[16.8px] text-[#999999] mb-2">
            Experience
          </div>

          <span class="font-normal text-sm leading-[16.8px] text-[#101828]">
            12 years
          </span>

        </section>

        <section class="flex gap-x-[10px] items-end mt-6">

          <div>

            <div class="font-normal text-sm leading-[16.8px] text-[#999999] mb-2">
              Phone Number
            </div>

            <span class="font-normal text-sm leading-[16.8px] text-[#101828]">
              +2348023456789
            </span>

          </div>
          
          <Button 
            variant="outline" 
            class="w-7 h-7 rounded-md border-[1.5px] border-[#3FA0FB] bg-white copy m-0 p-0"
          >
            <copy-two />
          </Button>

        </section>

        <section class="mt-6">

          <div class="font-normal text-sm leading-[16.8px] text-[#999999] mb-2">
            ID Number
          </div>

          <span class="font-normal text-sm leading-[16.8px] text-[#101828]">
            24156-65-0096
          </span>

        </section>

        <section class="mt-6">

          <div class="font-normal text-sm leading-[16.8px] text-[#999999] mb-2">
            License Plate
          </div>

          <span class="font-normal text-sm leading-[16.8px] text-[#101828]">
            TY9096
          </span>

        </section>

      </ScrollArea>
    </TabsContent>

    <TabsContent 
      value="customer-info"
      class="m-0 p-0"
    >
      <ScrollArea class="w-[321px] h-[248px]" >

        <section>

          <span class="font-normal text-sm leading-[16.8px] text-[#999999]">
            Reciever’s Name:
          </span>

          <div class="flex gap-x-2 items-center mt-2">
            <img 
              src="../../assets/pngs/baker-avatar.png"
              class="rounded-full border-[0.75px] border-[#000000] border-opacity-[0.08]"
            >
            <span class="font-medium text-sm text-[#101828]">
              Daniel Nwachuwu
            </span>
          </div>

        </section>

        <section class="flex gap-x-[10px] items-end mt-6">

          <div>

            <div class="font-normal text-sm leading-[16.8px] text-[#999999] mb-2">
              Reciever’s Number:
            </div>

            <span class="font-normal text-sm leading-[16.8px] text-[#101828]">
              +2348023456789
            </span>

          </div>
          
          <Button 
            variant="outline" 
            class="w-7 h-7 rounded-md border-[1.5px] border-[#3FA0FB] bg-white copy m-0 p-0"
          >
            <copy-two />
          </Button>

        </section>

        <section class="mt-6">

          <div class="font-normal text-sm leading-[16.8px] text-[#999999] mb-2">
            Reciever’s Email:
          </div>

          <span class="font-normal text-sm leading-[16.8px] text-[#101828]">
            Johndoe@email.com
          </span>

        </section>

      </ScrollArea>
    </TabsContent>

  </Tabs>
</template>

<style scoped>
.info {
  background-color: #F0F0F0;

  span {
    color: #060E1F;
  }
}
</style>