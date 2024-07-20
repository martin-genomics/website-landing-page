<script setup lang="ts">
import {
  DropdownMenu,
  DropdownMenuContent,
  DropdownMenuItem,
  DropdownMenuLabel,
  DropdownMenuSeparator,
  DropdownMenuTrigger,
} from '@/components/ui/dropdown-menu'
import { Icon } from '@iconify/vue'
import { Button } from '@/components/ui/button'
</script>

<template>
    <div class="flex items-center justify-around w-full h-14 fixed bg-white border-b border-gray-200 text-sm top-0">
        <h3 class="font-bold text-2xl text-gray-800">
          Martin Tembo
        </h3>

        <div>
          <ul class="flex items-center justify-center gap-3 text-gray-800">
              <RouterLink to="/">
                <li class="flex items-center justify-center hover:text-blue-700 font-body">
                  Home
                </li>
              </RouterLink>
            <RouterLink to="/">
              <li class="flex items-center justify-center hover:text-blue-700 font-body">
                Services
              </li>
            </RouterLink>
            <RouterLink to="/">
              <li class="flex items-center justify-center hover:text-blue-700 font-body">
                Details
              </li>
            </RouterLink>
            <RouterLink to="#features">
              <li class="flex items-center justify-center hover:text-blue-700 font-body">
                Features
              </li>
            </RouterLink>

            <li>
              <DropdownMenu>
                <DropdownMenuTrigger class="flex">
                <span>
                  Drop
                </span>
                  <Icon icon="mdi:chevron-down" class="text-2xl" :ssr="true"/>
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
            </li>
            <li class=" ">
              <Button class="bg-blue-600 rounded-2xl " size="default">
                  Get Quote
              </Button>
            </li>

          </ul>
        </div>
    </div>

</template>