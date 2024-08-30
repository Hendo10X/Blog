<script>
  import { onMount } from 'svelte';

  let currentDateTime = new Date();

  onMount(() => {
    const timer = setInterval(() => {
      currentDateTime = new Date();
    }, 1000);

    return () => clearInterval(timer);
  });

  $: formattedDateTime = new Intl.DateTimeFormat('en-US', {
    year: 'numeric',
    month: 'long',
    day: 'numeric',
    hour: '2-digit',
    minute: '2-digit',
    second: '2-digit',
    hour12: false
  }).format(currentDateTime);
</script>

<main class="min-h-screen bg-white text-gray-900 font-inter text-sm">
  <div class="max-w-xl mx-auto mt-8 mb-16 px-4 mt-10 p-10 py-20 px-2 ">
    <div class="flex justify-between items-center mb-1">
      <h1 class="text-xl font-bold">Dike-Benard Henderson</h1>
    </div>
    <p class="text-base text-gray-400 mb-4">{formattedDateTime}</p>
    
    <p class="mb-4 text-base">I was born in Nigeria, gonna travel the whole world.</p>
    
    <p class="mb-4 text-base">
      I'm building <a href="#" class="text-green-500 hover:underline">Muntant Inc</a>, 
      a user-first software company created with playfulness, interface and art in mind. We created 
      <a href="#" class="text-green-500 hover:underline">Sleekquest</a>, an e-commerce Saas for cutomizable branding and wears, and 
      <a href="#" class="text-green-500 hover:underline">Qiosk</a>, a sub-feature app for sleekquest which enables user to sell their brands to wider markets . 
      I'm currently working on a student based software, <a href="#" class="text-green-500 hover:underline">DocAcad</a>, 
      It enables students to share study resources round the globe.
    </p>
    
    <p class="mb-4 text-base">
      I also co-founded <a href="#" class="text-green-500 hover:underline">BoxSlashDot</a>. 
      We create and publish creative and wacky video games that you'd love to play, such as 
      <a href="#" class="text-green-500 hover:underline">graviton</a>.
    </p>
    
    <p class="mb-4 text-base">I consider myself a designer at heart and enjoy building highly polished products.</p>
    
    <p class="mb-4 text-base">
      You can reach me at <a href="https://twitter.com/boihendo" class="text-green-500 hover:underline">@boihendo</a> or 
      <a href="hendersondike@gmail.com" class="text-green-500 hover:underline">hendersondike@gmail.com</a>.
    </p>
    
    <div class="border-t border-gray-300 pt-2">
      <div class="flex justify-between items-center text-xs">
        <span>2024</span>
        <span class="font-medium">Building cool stuffs</span>
        <span>{currentDateTime.toLocaleDateString('en-US', { month: '2-digit', day: '2-digit' })}</span>
      </div>
    </div>
    
    <p class="text-xs text-gray-600 mt-4">Letting time pass...</p>
  </div>
</main>

<style global>
  @import url('https://fonts.googleapis.com/css2?family=Inter:wght@400;500;700&display=swap');
  
  @tailwind base;
  @tailwind components;
  @tailwind utilities;

  body {
    font-family: 'Inter', sans-serif;
  }
</style>