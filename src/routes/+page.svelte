<script>
	import Stylesheet from '../theme/Stylesheet.svelte';
	import { darkTheme } from '../theme/store.js';
	import Header from '../components/Header.svelte';
	import { Lottie } from 'lottie-svelte';
	$: dark = $darkTheme;
</script>

<Stylesheet />

<div class:dark>
	<div class="min-h-screen transition bg-gray-100 text-gray-800 dark:bg-gray-800 dark:text-white">
		<Header />
		<div class="max-w-4xl mx-auto px-4 sm:px-6 lg:px-8 pt-8">
			<h1 class="text-4xl font-bold mb-4">Welcome to Pariah Projects!</h1>
			<p class="text-lg mt-2">
				Welcome to Pariah Projects, where we embrace the spirit of being a "pariah" – an outlier, a
				rebel, a nonconformist. We stand out from the pack by offering custom web design and
				development services that are tailored to your specific needs and goals.
			</p>
		</div>
		<div class="flex justify-center -mt-16">
			<div class="max-w-3xl">
				<Lottie path="src/files/computer.json" speed={0.75} autoplay={true} loop={false} />
			</div>
		</div>
		<div class="max-w-4xl mx-auto px-4 sm:px-6 lg:px-8 py-8">
			<h1 class="text-4xl font-bold mb-4">With Pariah Projects, you can expect:</h1>
			<ul class="list-disc text-lg">
				<li class="mt-2 ml-4">
					Custom website design and development that is tailored to your specific needs and goals
				</li>
				<li class="mt-2 ml-4">
					User-friendly and responsive websites that work seamlessly on all devices
				</li>
				<li class="mt-2 ml-4">
					Integration of advanced features and functionality, such as e-commerce, social media
					integration, and more
				</li>
				<li class="mt-2 ml-4">
					Ongoing support and maintenance to ensure your website stays up-to-date and secure
				</li>
			</ul>
			<p class="text-lg mt-2">
				Ready to bring your vision to life? Contact us today to schedule a consultation and start
				building your dream website.
			</p>
		</div>
		<div class="max-w-4xl mx-auto px-4 sm:px-6 lg:px-8 py-8">
			<h1 class="text-4xl font-bold mb-4">Custom Web Design</h1>
			<div class="text-lg">
				<p class="mt-2">
					At Pariah Projects, we believe that every business deserves a website that is as unique
					and special as they are. That's why we offer custom web design and development services
					that are tailored to your specific needs and goals.
				</p>

				<p class="mt-2">
					Our team of skilled designers and developers will work closely with you to understand your
					vision and create a website that truly reflects your brand and values. Whether you need a
					simple brochure website or a more complex e-commerce platform, we have the expertise and
					experience to make it happen.
				</p>
				<p class="mt-2">
					We also offer a range of additional services, including SEO optimization, social media
					integration, and ongoing support and maintenance. With Pariah Projects, you can trust that
					your website will always be at the top of its game.
				</p>
				<p class="mt-2">
					Don't wait any longer to get the website you deserve – contact us today to start building
					your dream site!
				</p>
			</div>
		</div>
	</div>
</div>
