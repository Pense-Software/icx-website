<script>
	import Counter from './Counter.svelte';
	import welcome from '$lib/images/svelte-welcome.webp';
	import welcome_fallback from '$lib/images/svelte-welcome.png';
  	import { Parallax, ParallaxLayer, StickyLayer } from 'svelte-parallax';

  	import { Avatar, Button, Card, Carousel } from 'flowbite-svelte'
	import { offset } from '@popperjs/core';
	import Roadmap from './Roadmap.svelte';

	import app from '$lib/images/app.png'
	
	export const images = [
  {
    alt: "Intuitive Interface like Twitter",
    src: "https://i.ibb.co/vD1T5YS/Screenshot-2023-05-15-at-13-48-44.png",
    title: "seers.social",
  },
  {
    alt: "Prediction Markets",
    src: "https://i.ibb.co/RPbF56D/Screenshot-2023-05-15-at-14-39-42.png",
    title: "seers.social",
  },
  {
    alt: "User Profiles",
    src: "https://i.ibb.co/QvPBZst/Screenshot-2023-05-15-at-14-45-26.png",
    title: "seers.social",
  }
];
</script>

<svelte:head>
	<title>ICX</title>
	<meta name="description" content="ICX" />
</svelte:head>

<section class="w-full md:flex md:flex-row">
	<div class="flex flex-col gap-4 md:w-1/2 mt-4 p-4">
		<div class="text-4xl font-bold text-center">
			Web 3.0 Social Network
		</div>
		<div class="text-xl p-2">
			ICX is a cutting-edge web3 social network designed to embody the true principles of a decentralized internet. Built atop the revolutionary framework of the Internet Computer, it mirrors the functionalities you love on platforms like Twitter, but with enhanced privacy, ownership, and community-driven governance. 
		</div>
		<div class="flex justify-center">
      <a href="https://oulla-fyaaa-aaaag-qa6fa-cai.ic0.app/" role="link" class="text-center font-medium focus:outline-none inline-flex items-center justify-center px-5 py-3 text-base text-white bg-purple-700 hover:bg-purple-800 dark:bg-purple-600 dark:hover:bg-purple-700 rounded-lg">Enter Demo</a>
			<!-- <Button class="text-center font-medium focus:outline-none inline-flex items-center justify-center px-5 py-3 text-base text-white bg-purple-700 hover:bg-purple-800 dark:bg-purple-600 dark:hover:bg-purple-700 rounded-lg" href="https://oulla-fyaaa-aaaag-qa6fa-cai.ic0.app/" size="lg">Enter Demo</Button> -->
		</div>
	</div>
	<div class="flex flex-col md:w-1/2 mt-4 p-4">
		<img src={app} alt="" class="rounded-lg"/>
	</div> 
</section>

<section class="w-full flex flex-row gap-4 md:gap-8 text-2xl justify-center mt-8 p-8">
	<div ><span class="numposts"/>K Posts</div>
	<div><span class="numu"/>K Users</div>
  <div>$<span class="numtvl"/>K TVL</div>
	<div>$<span class="numr"/>K Revenue</div>
</section>


<section class="w-full flex flex-row gap-8 text-2xl justify-center mt-4 p-4">
	<div class="shadow ">
		<div class="md:flex md:flex-row w-full">
			<div class="md:w-1/2 p-4 text-xl">
				<h3 class="font-medium mb-2 text-purple-500">Weekly Rewards</h3>
				ICX is a social network that rewards your activity with weekly ICP/ICX tokens. Engage and contribute to earn rewards, revolutionizing the fusion of social media and token economics in one platform.
			</div>
      <div class="md:w-1/2 p-4">
				<img src="https://i.ibb.co/ByCqhQx/Screenshot-2023-05-15-at-15-31-23.png" class="rounded" />
			</div>
		</div>
	</div>
</section>


<section class="w-full flex flex-row gap-8 text-2xl justify-center mt-4 p-4">
	<div class="shadow ">
		<div class="md:flex md:flex-row w-full">
			<div class="md:w-1/2 p-4 text-xl">
				<h3 class="font-medium mb-2 text-purple-500">Prediction Markets</h3>
				<p>In ICX, you can create, resolve, and participate in prediction markets. These markets allow users to make predictions about future events, leveraging the collective wisdom of the community.</p> 
				<p class="pt-4">By accurately predicting outcomes, users have the opportunity to win ICP tokens as a reward for their correct predictions.</p>
				<p class="pt-4">Prediction markets are resolved using token voting and a decentralised sports oracle.</p>
			</div>
      <div class="md:w-1/2 p-4">
				<img src="https://i.ibb.co/DW5WLmt/Screenshot-2023-05-15-at-15-47-16.png" class="rounded" />
			</div>
		</div>
	</div>
</section>

<Roadmap></Roadmap>

<style>

body{
	counter-reset: nump;
	counter-reset: numt;
	counter-reset: numr;
}

@property --nump {
  syntax: "<integer>";
  initial-value: 12;
  inherits: false;
}

.numposts {
  animation: postscnt 3s 1 ease-out;
  counter-reset: nump var(--nump);
  font: 500 24px system-ui;
}
.numposts::before {
	content: counter(nump);
}


@keyframes postscnt {
  from {
    --nump: 0;
  }
  to {
    --nump: 12;
  }
}

@property --numt {
  syntax: "<integer>";
  initial-value: 15;
  inherits: false;
}

.numtvl {
  animation: tvlcnt 3s 1 ease-out;
  counter-reset: numt var(--numt);
  font: 500 24px system-ui;
}
.numtvl::before {
	content: counter(numt);
}

@keyframes tvlcnt {
  from {
    --numt: 0;
  }
  to {
    --numt: 15;
  }
}

@property --numu {
  syntax: "<integer>";
  initial-value: 3;
  inherits: false;
}

.numu {
  animation: ucnt 3s 1 ease-out;
  counter-reset: numu var(--numu);
  font: 500 24px system-ui;
}
.numu::before {
	content: counter(numu);
}

@keyframes ucnt {
  from {
    --numu: 0;
  }
  to {
    --numu: 3;
  }
}




@property --numr {
  syntax: "<integer>";
  initial-value: 25;
  inherits: false;
}

.numr {
  animation: rcnt 3s 1 ease-out;
  counter-reset: numr var(--numr);
  font: 500 24px system-ui;
}
.numr::before {
	content: counter(numr);
}

@keyframes rcnt {
  from {
    --numr: 0;
  }
  to {
    --numr: 25;
  }
}

</style>