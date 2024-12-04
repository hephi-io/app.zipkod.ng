<script setup>
import { ref } from "vue";

import { Input } from "@/components/ui/input";
import {
  DropdownMenu,
  DropdownMenuContent,
  DropdownMenuItem,
  DropdownMenuLabel,
  DropdownMenuSeparator,
  DropdownMenuTrigger,
} from "@/components/ui/dropdown-menu";
import { Button } from "@/components/ui/button";
import { ToggleGroup, ToggleGroupItem } from "@/components/ui/toggle-group";
import { Tabs, TabsContent, TabsList, TabsTrigger } from '@/components/ui/tabs';
import { Badge } from '@/components/ui/badge';

import infoTabComponent from "@/components/shared/info-tab-component.vue";

import MagnifyingGlassIcon from "@/assets/svgs/magnifying-glass-icon.svg";
import ArrowDataTransfer from "@/assets/svgs/arrow-data-transfer-vertical-round.svg";
import ChevronDown from "@/assets/svgs/chevron-down-sharp.svg";
import FunnelSimple from "@/assets/svgs/FunnelSimple.svg";
import LocationShare from "@/assets/svgs/location-share-02.svg";
import Copy from "@/assets/svgs/copy-01.svg";
import Navigation from "@/assets/svgs/navigation-01.svg";
import PinLocation from "@/assets/svgs/pin-location-03.svg";
import VerticalDivider from "@/assets/svgs/vertical-divider.svg";
import LocationIcon from "@/assets/svgs/location-icon.svg";
import Ellipse from "@/assets/svgs/ellipse-icon.svg";
import RectangleIcon from "@/assets/svgs/rectangle-icon.svg";
import PlusSign from "@/assets/svgs/plus-sign-1.svg";
import MinusSign from "@/assets/svgs/minus-sign.svg";
import LocationOrange from "@/assets/svgs/location-orange.svg";


// TOGGLE
const people = [
  { value: "coco", name: "Coco's Bespoke" },
  { value: "damien-01", name: "Damien Smith" },
  { value: "damien-02", name: "Damien Smith" },
  { value: "damien-03", name: "Damien Smith" },
];

const notSelectedToggleTabStyle = "w-full h-[200px] rounded-lg border border-[#E4E7EC] p-4 mb-6";
const selectedToggleTabStyle = "w-full h-[200px] rounded-lg border border-[#F1C49B] p-4 mb-6 toggle";

const selectedToggleTab = ref("coco");

const selectToggleTab = (value) => {
  selectedToggleTab.value = value;
  console.log(selectedToggleTab.value);
}


// HORIZONTAL TAB
const selectedHorizontalTab = ref("map-based-tracking");
const horizontalTabValues = [ "map-based-tracking", "status-based-tracking" ]
const [ horizontalTabValue1, horizontalTabValue2 ] = horizontalTabValues;
const selectedHorizontalTabStyle = "w-[181.99px] rounded px-3 py-[6px] tabs-trigger";
const notSelectedHorizontalTabStyle = "w-[181.99px] rounded px-3 py-[6px]";

const selectHorizotalTab = (value) => {
  selectedHorizontalTab.value = value;
  console.log(selectedHorizontalTab.value);
}
</script>

<template>
  <div>

    <header class="py-3 mb-9">
      <span
        class="space-mono font-semibold text-2xl leading-6 tracking-[-0.03em] text-[#060E1F]"
      >
        Tracking
      </span>
    </header>

    <section class="flex gap-x-6 items-start">

      <section class="w-[299px]">

        <section class="flex gap-x-2 items-center mb-4">

          <div class="relative w-[129px] items-center">

            <Input
              id="search"
              type="text"
              placeholder="Search..."
              class="rounded border border-[#D4D4D4] pl-8 pr-[10px] py-[10px] font-normal text-sm leading-[14px] tracking-[-0.03em] text-[#C9C8CF]"
            />

            <span
              class="absolute start-0 inset-y-0 flex items-center justify-center pl-2"
            >
              <MagnifyingGlassIcon class="text-muted-foreground" />
            </span>

          </div>

          <DropdownMenu>

            <DropdownMenuTrigger>
              <Button
                variant="outline"
                class="rounded border border-[#D4D4D4] px-3 py-2 gap-x-2 bg-white"
              >

                <ArrowDataTransfer />

                <span class="font-medium text-sm leading-[21px] text-[#404D61]">
                  Status
                </span>

                <ChevronDown class="-rotate-90" />

              </Button>
            </DropdownMenuTrigger>

            <DropdownMenuContent>

              <DropdownMenuLabel>My Account</DropdownMenuLabel>
              <DropdownMenuSeparator />
              <DropdownMenuItem>Profile</DropdownMenuItem>
              <DropdownMenuItem>Billing</DropdownMenuItem>
              <DropdownMenuItem>Team</DropdownMenuItem>
              <DropdownMenuItem>Subscription</DropdownMenuItem>

            </DropdownMenuContent>

          </DropdownMenu>

          <DropdownMenu>

            <DropdownMenuTrigger>
              <Button
                variant="outline"
                class="rounded border border-[#D4D4D4] px-3 py-2 bg-white"
              >
                <FunnelSimple />
              </Button>
            </DropdownMenuTrigger>

            <DropdownMenuContent>

              <DropdownMenuLabel>My Account</DropdownMenuLabel>
              <DropdownMenuSeparator />
              <DropdownMenuItem>Profile</DropdownMenuItem>
              <DropdownMenuItem>Billing</DropdownMenuItem>
              <DropdownMenuItem>Team</DropdownMenuItem>
              <DropdownMenuItem>Subscription</DropdownMenuItem>

            </DropdownMenuContent>

          </DropdownMenu>

        </section>

        <ToggleGroup type="single" class="block">

          <ToggleGroupItem
            :value="person.value"
            :class="[selectedToggleTab === person.value ?selectedToggleTabStyle :notSelectedToggleTabStyle]"
            v-for="(person, index) in people"
            :key="index"
            @click="selectToggleTab(person.value)"
          >
            <div class="w-full h-full">

              <section class="flex justify-between items-center mb-2">

                <div
                  class="rounded border border-[#E4E7EC] p-1 bg-[#F9FAFB] flex gap-x-2 items-center tag"
                >
                  <span class="font-normal text-xs leading-5 text-[#475467]">
                    #DR3E4478
                  </span>
                  <copy />
                </div>

                <LocationShare class="icon" />

              </section>

              <section>

                <section class="mb-4">

                  <section class="flex justify-between items-center mb-4">

                    <div class="flex gap-x-2 items-center">
                      <Navigation />
                      <span class="font-medium text-sm text-[#475467]">
                        {{ person.name }}
                      </span>
                    </div>

                    <span class="font-normal text-xs leading-5 text-[#475467]">
                      91km
                    </span>

                  </section>

                  <section>

                    <div class="flex gap-x-2 items-center mb-1">
                      <PinLocation />
                      <span
                        class="font-normal text-xs leading-[15.6px] text-[#475467]"
                      >
                        17, Ogunyemi strt, Magodo.
                      </span>
                    </div>

                    <VerticalDivider class="mb-1" />

                    <div class="flex gap-x-2 items-center mb-1">
                      <LocationIcon />
                      <span
                        class="font-normal text-xs leading-[15.6px] text-[#475467]"
                      >
                        Shop 10/644 GorgerSt, Sydney NSW 2000
                      </span>
                    </div>

                  </section>

                </section>

                <section class="flex gap-x-2 items-center">
                  <span class="font-normal text-xs leading-5 text-[#37404D80]">
                    2h 23m
                  </span>
                  <Ellipse />
                  <span class="font-normal text-xs leading-5 text-[#37404D80]">
                    34km
                  </span>
                </section>

              </section>

            </div>
          </ToggleGroupItem>

        </ToggleGroup>

      </section>

      <section class="flex-grow rounded-xl border border-[#E4E7EC] shadow-sm shadow-[#1018280D]">
        <Tabs :default-value="horizontalTabValue1">

          <div class="px-6 py-5">

            <section class="flex justify-between items-center mb-4">

              <div class="font-semibold text-base leading-7 text-[#101828]">
                Order Number: <span class="font-normal">#DR3E4478</span>
              </div>

              <Badge 
                variant="secondary"
                class="rounded-md border border-[#E8F4FF] px-4 py-2 bg-[#F0F4F9] shadow-sm shadow-[#1018280D]"
              >
                <span class="font-medium text-sm leading-[18px] text-center text-[#309BFF]">
                  In transit
                </span>
              </Badge>

            </section>

            <TabsList class="w-[373.99px] rounded-lg p-[5px] bg-[#F5F7FA]">

              <TabsTrigger 
                :value="horizontalTabValue1"
                :class="selectedHorizontalTab === horizontalTabValue1 ? selectedHorizontalTabStyle : notSelectedHorizontalTabStyle"
                @click="selectHorizotalTab(horizontalTabValue1)"
              >
                <span class="font-medium text-sm text-[#878FA1]">
                  Map-Based Tracking
                </span>
              </TabsTrigger>

              <TabsTrigger 
                :value="horizontalTabValue2"
                :class="selectedHorizontalTab === horizontalTabValue2 ? selectedHorizontalTabStyle : notSelectedHorizontalTabStyle"
                @click="selectHorizotalTab(horizontalTabValue2)"
              >
                <span class="font-medium text-sm text-[#878FA1]">
                  Status-Based Tracking
                </span>
              </TabsTrigger>

            </TabsList>

          </div>

          <TabsContent value="map-based-tracking">
            <div class="relative">

              <img 
                src="../assets/pngs/mapsicle-map.png" 
                class="object-cover border-t"
              />

              <info-tab-component />

              <div class="absolute right-[89.56px] bottom-4 w-[155.66px] h-[54px] flex gap-x-[10px] items-center rounded-lg border border-[#F4F4F4] p-2 bg-white box box-content">

                <location-orange class="m-0 p-0 rounded-full" />

                <div>

                  <span class="font-semibold text-[11px] leading-[13.31px] tracking-[0.01em] text-[#232323]">
                    8502 Preston 
                  </span>

                  <div class="font-normal text-[10px] leading-[12.1px] tracking-[0.01em] text-[#B0B0B0] mt-[1px]">
                    Rd. Inglewood, Maine 98380
                  </div>

                </div>

              </div>

              <div class="absolute right-4 bottom-4 w-[34.51px] h-[115.63px]">

                <section class="w-[33px] h-[70.13px] flex flex-col items-center bg-white rounded">

                  <Button 
                    variant="ghost"
                    class="w-full h-1/2 m-0 p-0"   
                  >
                    <plus-sign />
                  </Button>

                  <div class="w-[70%] border-b"></div>

                  <Button 
                    variant="ghost"
                    class="w-full h-1/2 m-0 p-0"
                  >
                    <minus-sign />
                  </Button>

                </section>

                <Button
                  variant="ghost" 
                  class="w-[34.51px] h-[34.51px] flex justify-center items-center rounded-full border border-[#F4F4F4] bg-white mt-[11px] p-0"
                >
                  <rectangle-icon />
                </Button>

              </div>

            </div>
          </TabsContent>

          <TabsContent value="status-based-tracking">
            <div class="h-[636px] relative">
              <info-tab-component class="border border-[#E4E7EC] info-tab-shadow" />
            </div>
          </TabsContent>

        </Tabs>
      </section>

    </section>

  </div>
</template>

<style lang="css" scoped>
.toggle {
  background: #fffbf8;

  .tag {
    background: white;
  }

  .icon {
    stroke: #ff7830;
  }
}

.tabs-trigger {
  border-radius: 3px;
  background-color: white;
  box-shadow: 0px 3px 1px 0px #0000000A;
  box-shadow: 0px 3px 8px 0px #0000001F;

  span {
    color: #0F172A;
  }
}

.info {
  background-color: #F0F0F0;

  span {
    color: #060E1F;
  }
}

.box {
  box-shadow: 0px 13px 34px 0px #FFD1C04D;
}

.copy {
  box-shadow: 0px 4px 12px 0px #3FA0FB40;
}

.info-tab-shadow {
  box-shadow: 0px 4px 16px 0px #AEC8FF26;
}

/* 

*/
</style>
