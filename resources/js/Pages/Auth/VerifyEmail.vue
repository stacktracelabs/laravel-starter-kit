<template>
  <AuthLayout title="Verify email" description="Please verify your email address by clicking on the link we just emailed to you.">
    <Head title="Email verification"/>

    <div v-if="status === 'verification-link-sent'" class="mb-4 text-center text-sm font-medium text-green-600">
      A new verification link has been sent to the email address you provided during registration.
    </div>

    <form @submit.prevent="submit" class="space-y-6 text-center">
      <Button :disabled="form.processing" variant="secondary" :processing="form.processing">
        Resend verification email
      </Button>

      <TextLink :href="route('logout')" method="post" as="button" class="mx-auto block text-sm"> Log out
      </TextLink>
    </form>
  </AuthLayout>
</template>

<script setup lang="ts">
import TextLink from '@/Components/TextLink.vue';
import { Button } from '@/Components/Button';
import AuthLayout from '@/Layouts/AuthLayout.vue';
import { Head, useForm } from '@inertiajs/vue3';

defineProps<{
  status?: string;
}>();

const form = useForm({});

const submit = () => {
  form.post(route('verification.send'));
};
</script>
