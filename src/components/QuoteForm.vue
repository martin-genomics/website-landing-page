<script setup lang="ts">
import { h } from 'vue'
import { useForm } from 'vee-validate'
import { toTypedSchema } from '@vee-validate/zod'
import * as z from 'zod'

import { Button } from '@/components/ui/button'
import {
  FormControl,
  FormDescription,
  FormField,
  FormItem,
  FormLabel,
  FormMessage,
} from '@/components/ui/form'
import { Input } from '@/components/ui/input'
import { toast } from '@/components/ui/toast'

const formSchema = toTypedSchema(z.object({
  username: z.string().min(2).max(50),
}))

const { handleSubmit } = useForm({
  validationSchema: formSchema,
})

const onSubmit = handleSubmit((values) => {
  toast({
    title: 'You submitted the following values:',
    description: h('pre', { class: 'mt-2 w-[340px] rounded-md bg-slate-950 p-4' }, h('code', { class: 'text-white' }, JSON.stringify(values, null, 2))),
  })
})
</script>

<template>
  <form class="w-2/3 flex flex-col gap-4 " @submit.prevent="onSubmit">
    <FormField v-slot="{ componentField }" name="name">
      <FormItem>
        <FormControl>
          <Input type="text" class="p-5" placeholder="Name" v-bind="componentField" />
        </FormControl>
        <FormMessage />
      </FormItem>
    </FormField>

    <FormField v-slot="{ componentField }" name="email">
      <FormItem>
        <FormControl>
          <Input type="email" class="p-5" placeholder="Email" v-bind="componentField" />
        </FormControl>
        <FormMessage />
      </FormItem>
    </FormField>

    <FormField v-slot="{ componentField }" name="industry">
      <FormItem>
        <FormControl>
          <Input type="text" class="p-5" placeholder="Industry" v-bind="componentField" />
        </FormControl>
        <FormMessage />
      </FormItem>
    </FormField>
    <FormField v-slot="{ componentField }" name="product">
      <FormItem>
        <FormControl>
          <Input type="text" class="p-5" placeholder="Product" v-bind="componentField" />
        </FormControl>

        <FormMessage />
      </FormItem>
    </FormField>


    <Button type="submit" class="bg-blue-600 rounded-lg">
      Submit
    </Button>
  </form>
</template>