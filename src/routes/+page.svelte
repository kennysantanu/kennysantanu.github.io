<script lang="ts">
	import { base } from '$app/paths';
</script>

<svelte:head>
	<title>Kenny Santanu | Portfolio</title>
</svelte:head>

<div id="about" class="grid grid-rows-[auto_1fr_auto]">
	<!-- Header -->
	<header
		class="@container sticky top-0 z-10 flex items-center justify-between border-b border-solid border-b-[#2c3135] bg-[#1e2124] px-4 py-3 whitespace-nowrap md:px-10"
	>
		<div class="flex items-center gap-4 text-white">
			<div class="hidden md:block">
				<img
					src="{base}/picture.jpg"
					alt="Kenny Santanu"
					class="aspect-square size-10 rounded-full bg-cover bg-center bg-no-repeat object-cover"
				/>
			</div>
			<h2 class="text-lg leading-tight font-bold tracking-[-0.015em] text-white">Portfolio</h2>
		</div>
		<div class="flex flex-1 justify-end gap-8">
			<div class="flex items-center gap-9">
				<a class="text-sm leading-normal font-medium text-white" href="#about">About</a>
				<a class="text-sm leading-normal font-medium text-white" href="#projects">Projects</a>
			</div>
		</div>
	</header>
	<!-- Page -->
	<div class="container mx-auto grid grid-cols-1">
		<!-- Main -->
		<main class="flex flex-1 justify-center py-5">
			<div class="layout-content-container flex max-w-[960px] flex-1 flex-col">
				<div class="@container flex p-4">
					<div class="flex w-full flex-col items-center gap-4">
						<div class="flex flex-col items-center gap-4">
							<div
								class="aspect-square min-h-32 w-32 rounded-full bg-cover bg-center bg-no-repeat"
								style="background-image: url('{base}/picture.jpg');"
							></div>
							<div class="flex flex-col items-center justify-center">
								<p
									class="text-center text-[22px] leading-tight font-bold tracking-[-0.015em] text-white"
								>
									Kenny Santanu
								</p>
								<p class="text-center text-base leading-normal font-normal text-[#a2abb3]">
									Software Engineer | IT Consultant
								</p>
								<p class="text-center text-base leading-normal font-normal text-[#a2abb3]">
									Based in Los Angeles, CA
								</p>
							</div>
						</div>
					</div>
				</div>
				<p class="px-4 pt-1 pb-3 text-center text-base leading-normal font-normal text-white">
					I'm a Software Engineer and IT Consultant with a passion for building innovative solutions
					that address real-world challenges. With a strong foundation in software development and
					IT consulting, I combine technical expertise with a passion for problem-solving to deliver
					impactful applications and drive business success.
				</p>
				<div class="flex justify-center px-4 py-3">
					<a
						href="https://www.linkedin.com/in/kennysantanu/"
						target="_blank"
						rel="noopener noreferrer"
						class="flex h-10 max-w-[480px] min-w-[84px] cursor-pointer items-center justify-center gap-2 overflow-hidden rounded-full bg-[#2c3135] px-4 pl-4 text-sm leading-normal font-bold tracking-[0.015em] text-white no-underline"
					>
						<div class="text-white" data-icon="LinkedinLogo" data-size="20px" data-weight="regular">
							<img src="{base}/linkedin-icon.png" alt="LinkedIn Icon" class="h-5 w-5" />
						</div>
						<span class="truncate">Connect on LinkedIn</span>
					</a>
				</div>
				<h2
					id="projects"
					class="px-4 pt-5 pb-3 text-[22px] leading-tight font-bold tracking-[-0.015em] text-white"
				>
					Projects
				</h2>
				<div class="grid grid-cols-[repeat(auto-fit,minmax(224px,1fr))] gap-3 p-4">
					<div class="flex flex-col gap-3 pb-3">
						<div
							class="aspect-video w-full rounded-xl bg-cover bg-center bg-no-repeat"
							style="background-image: url('{base}/denials-tracker-image.jpg');"
						></div>
						<div>
							<p class="text-base leading-normal font-medium text-white">Denials Tracker</p>
							<p class="text-sm leading-normal font-normal text-[#a2abb3]">
								I designed, developed, and implemented a progressive web application to streamline
								the investigation and resolution of insurance claim denials. Deployed locally
								on-premise at our clinic, the application enabled the recovery of over $60,000 in
								previously denied claims within its first year of use. The application utilizes the
								SvelteKit frontend framework, Skeleton UI component library, Supabase for backend
								services, and AG Grid Community for advanced data grid display. Both the frontend
								and backend are configurable for online or on-premise hosting, ensuring that
								protected patient data remains securely within the clinic environment.
							</p>
						</div>
						<div class="flex flex-wrap gap-3 pr-4">
							<div
								class="flex h-8 shrink-0 items-center justify-center space-x-1 rounded-full bg-[#2c3135] pr-4 pl-4"
							>
								<img src="{base}/svelte-icon.png" alt="Svelte Icon" class="h-7 w-7 p-1" />
								<p class="text-sm leading-normal font-medium text-white">Svelte</p>
							</div>
							<div
								class="flex h-8 shrink-0 items-center justify-center space-x-1 rounded-full bg-[#2c3135] pr-4 pl-4"
							>
								<img src="{base}/skeleton-ui-icon.png" alt="Skeleton UI Icon" class="h-7 w-7 p-1" />
								<p class="text-sm leading-normal font-medium text-white">Skeleton UI</p>
							</div>
							<div
								class="flex h-8 shrink-0 items-center justify-center space-x-1 rounded-full bg-[#2c3135] pr-4 pl-4"
							>
								<img src="{base}/supabase-icon.svg" alt="Supabase Icon" class="h-7 w-7 p-1" />
								<p class="text-sm leading-normal font-medium text-white">Supabase</p>
							</div>
							<div
								class="flex h-8 shrink-0 items-center justify-center space-x-1 rounded-full bg-[#2c3135] pr-4 pl-4"
							>
								<img src="{base}/ag-grid-icon.png" alt="AG Grid Icon" class="h-7 w-7 p-1" />
								<p class="text-sm leading-normal font-medium text-white">AG Grid</p>
							</div>
							<div
								class="flex h-8 shrink-0 items-center justify-center space-x-1 rounded-full bg-[#2c3135] pr-4 pl-4"
							>
								<img src="{base}/typescript-icon.png" alt="TypeScript Icon" class="h-7 w-7 p-1" />
								<p class="text-sm leading-normal font-medium text-white">TypeScript</p>
							</div>
						</div>
					</div>
					<div class="flex flex-col gap-3 pb-3">
						<div
							class="aspect-video w-full rounded-xl bg-cover bg-center bg-no-repeat"
							style="background-image: url('{base}/portfolio-image.jpg');"
						></div>
						<div>
							<p class="text-base leading-normal font-medium text-white">Portfolio Website</p>
							<p class="text-sm leading-normal font-normal text-[#a2abb3]">
								This website showcases my portfolio, built with Svelte and TypeScript. It features a
								responsive design and a clean layout with Tailwind CSS to highlight my projects and
								skills. The site is optimized for performance and accessibility, ensuring a great
								user experience across devices.
							</p>
						</div>
						<div class="flex flex-wrap gap-3 pr-4">
							<div
								class="flex h-8 shrink-0 items-center justify-center space-x-1 rounded-full bg-[#2c3135] pr-4 pl-4"
							>
								<img src="{base}/svelte-icon.png" alt="Svelte Icon" class="h-7 w-7 p-1" />
								<p class="text-sm leading-normal font-medium text-white">Svelte</p>
							</div>
							<div
								class="flex h-8 shrink-0 items-center justify-center space-x-1 rounded-full bg-[#2c3135] pr-4 pl-4"
							>
								<img src="{base}/javascript-icon.png" alt="JavaScript Icon" class="h-7 w-7 p-1" />
								<p class="text-sm leading-normal font-medium text-white">JavaScript</p>
							</div>
							<div
								class="flex h-8 shrink-0 items-center justify-center space-x-1 rounded-full bg-[#2c3135] pr-4 pl-4"
							>
								<img src="{base}/typescript-icon.png" alt="TypeScript Icon" class="h-7 w-7 p-1" />
								<p class="text-sm leading-normal font-medium text-white">TypeScript</p>
							</div>
							<div
								class="flex h-8 shrink-0 items-center justify-center space-x-1 rounded-full bg-[#2c3135] pr-4 pl-4"
							>
								<img src="{base}/html-icon.png" alt="HTML Icon" class="h-7 w-7 p-1" />
								<p class="text-sm leading-normal font-medium text-white">HTML</p>
							</div>
							<div
								class="flex h-8 shrink-0 items-center justify-center space-x-1 rounded-full bg-[#2c3135] pr-4 pl-4"
							>
								<img
									src="{base}/tailwind-css-icon.png"
									alt="Tailwind CSS Icon"
									class="h-7 w-7 p-1"
								/>
								<p class="text-sm leading-normal font-medium text-white">Tailwind CSS</p>
							</div>
						</div>
					</div>					
				</div>
			</div>
		</main>
		<!-- </main> -->
	</div>
	<!-- Footer -->
	<footer class="flex items-center justify-center px-10 py-3 text-xs whitespace-nowrap">
		© 2025 Kenny Santanu
	</footer>
</div>
