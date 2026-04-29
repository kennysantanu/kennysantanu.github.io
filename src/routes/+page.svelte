<script lang="ts">
	import { base } from '$app/paths';
	import Linkedin from '@lucide/svelte/icons/linkedin';
	import Github from '@lucide/svelte/icons/github';
	import MapPin from '@lucide/svelte/icons/map-pin';
	import Menu from '@lucide/svelte/icons/menu';
	import X from '@lucide/svelte/icons/x';

	let mobileMenuOpen = $state(false);
	const navLinks = [
		{ href: '#about', label: 'About' },
		{ href: '#experience', label: 'Experience' },
		{ href: '#projects', label: 'Projects' },
		{ href: '#skills', label: 'Skills' },
		{ href: '#contact', label: 'Contact' }
	];
	import Award from '@lucide/svelte/icons/award';
	import GraduationCap from '@lucide/svelte/icons/graduation-cap';
	import Briefcase from '@lucide/svelte/icons/briefcase';
	import Wrench from '@lucide/svelte/icons/wrench';
	import Sparkles from '@lucide/svelte/icons/sparkles';
	import ArrowRight from '@lucide/svelte/icons/arrow-right';
	import Quote from '@lucide/svelte/icons/quote';

	const impact = [
		{ value: '$60K+', label: 'recovered in denied claims, year one of the AI denial tracker' },
		{ value: '80%', label: 'less time spent on manual billing after automation' },
		{ value: '30 days', label: 'EHR migration, zero downtime, 100% staff adoption' },
		{ value: '2,700+', label: 'PMI Los Angeles members served as Director of the Website' }
	];

	const credentials = [
		{ title: 'PMP', subtitle: 'Project Management Professional', org: 'Project Management Institute' },
		{ title: 'CAPM', subtitle: 'Certified Associate in Project Management', org: 'Project Management Institute' },
		{ title: 'M.S.', subtitle: 'Information Technology Management', org: 'Western Governors University' },
		{ title: 'B.S.', subtitle: 'Computer Science, Minor in Data Science', org: 'Cal Poly Pomona' }
	];

	const experience = [
		{
			role: 'Healthcare Revenue Cycle and Project Manager',
			org: 'Jonardi Handoko, M.D.',
			location: 'Upland, CA',
			period: 'Aug 2017 to Present',
			bullets: [
				'Designed and deployed an AI powered denial tracking system that recovered over $60,000 in underpaid and denied claims within the first year.',
				'Led an emergency EHR migration in under 30 days with zero downtime and 100% staff adoption after a vendor data loss event.',
				'Implemented billing automation that cut processing time by up to 80% and freed staff to focus on patient facing work.',
				'Coordinate technology infrastructure refresh projects with zero service interruptions.',
				'Manage end to end healthcare revenue cycle operations for the practice.'
			]
		},
		{
			role: 'Director of the Website',
			org: 'PMI Los Angeles Chapter',
			location: 'Los Angeles, CA',
			period: 'Sep 2025 to Present',
			bullets: [
				'Maintain pmi-la.org with 99.9% uptime, serving more than 2,700 chapter members.',
				'Run monthly training for new volunteers through documentation and hands on sessions.',
				'Coordinate with vendor Dark Rhino on enhancements that improve member resources and engagement.',
				'Partner with cross functional chapter teams on website projects from intake through release.'
			]
		}
	];

	const projects = [
		{
			title: 'AI Denial Tracking System',
			outcome: 'Recovered $60,000+ in year one. Built and deployed inside an active clinic.',
			description:
				'A progressive web app that streamlines investigation and resolution of insurance claim denials. The system gives next step recommendations, drafts appeal letters, checks payment status, and auto closes resolved denials. Deployed on premise so protected patient data never leaves the clinic.',
			role: 'Designer, builder, and operator. Worked with billing staff to define workflows, then implemented the full stack and trained the team.',
			image: 'denials-tracker-image.jpg',
			tech: ['Svelte', 'Skeleton UI', 'Supabase', 'AG Grid', 'TypeScript']
		},
		{
			title: 'EHR Emergency Migration Case Study',
			outcome: '30 day cutover, zero downtime, 100% staff adoption.',
			description:
				'After repeated data loss events with the prior EHR vendor, I led an emergency migration from Aura by Sigmund Software to OfficeAlly EHR. Scoped vendor evaluation, data migration, parallel testing, training plan, and go live in under 30 days while keeping the clinic running.',
			role: 'Project lead. Vendor selection, data mapping, training plan, change management, and cutover.',
			image: '',
			tech: ['EHR Implementation', 'Vendor Management', 'Change Management', 'Training', 'Data Migration']
		},
		{
			title: 'Production AI Agent Workflow',
			outcome: 'Daily use of self hosted and frontier AI agents for clinic operations and personal productivity.',
			description:
				'Architect and operate AI agent stacks using OpenClaw, local model runtimes such as LM Studio and Ollama, and frontier APIs. Hands on experience with prompt design, tool use, evaluation, governance, and the kinds of failure modes most healthcare teams have not yet seen in the wild.',
			role: 'Architect and operator. Bridge between healthcare operations and applied AI.',
			image: '',
			tech: ['OpenClaw', 'LM Studio', 'Ollama', 'Python', 'AI Governance']
		},
		{
			title: 'AI Discord Bot',
			outcome: 'Personal lab for testing emerging AI techniques in a sandboxed setting.',
			description:
				'An ongoing experimental platform built with discord.py for integrating new open source and self hosted AI capabilities. Includes an LLM chatbot, image generation, text to speech, and other modules I rotate in as the field moves.',
			role: 'Sole developer. Use this project to stay current on the model landscape and tool ecosystem.',
			image: 'ai-discord-bot-image.jpg',
			tech: ['Python', 'PyTorch', 'Ollama', 'Discord', 'Docker']
		},
		{
			title: 'SAM2 Image Segmentation and Replacement',
			outcome: 'Hands on integration of a frontier vision model into a working web app.',
			description:
				'A Python web app that lets a user draw a rough mask, then uses Meta Segment Anything Model 2 to refine the mask for precise segmentation and seamless region replacement. Demonstrates comfort wiring deep learning models into real interfaces.',
			role: 'Sole developer.',
			image: 'sam2-image.jpg',
			tech: ['Python', 'Gradio', 'OpenCV', 'Meta AI', 'Hugging Face']
		},
		{
			title: 'YOLOv8 Traffic Sign Detection from Scratch',
			outcome: '3,078 labeled images. Real dashcam footage. Trained without pre-trained weights.',
			description:
				'A computer vision model built to detect and classify 17 categories of California traffic signs and signals, including stop signs, speed limits, and traffic light states. Collected hours of dashcam footage across seven SoCal cities, annotated every image manually in Roboflow, and trained YOLOv8 from scratch across three dataset iterations. The core finding: scaling data volume alone does not close the performance gap. Labeling consistency and architecture selection matter more. A final experiment with COCO pre-trained weights reached approximately 70% mAP.',
			role: 'Co-researcher and primary dataset contributor. Personally annotated 1,344 images across all three dataset versions. Co-designed the training pipeline, ran local experiments on an RTX 3090, and co-authored the published research paper.',
			image: '',
			tech: ['Python', 'PyTorch', 'YOLOv8', 'Roboflow', 'Google Colab', 'Jupyter Notebook', 'Computer Vision']
		}
	];

	const skills = {
		'Project Management': [
			'PMP and CAPM certified',
			'Agile, Scrum, Waterfall, Hybrid',
			'Full project lifecycle, initiation through closing',
			'Cross functional coordination',
			'Vendor evaluation and management',
			'Stakeholder communication and business analysis'
		],
		'Healthcare': [
			'EHR implementation and migration',
			'Revenue cycle management',
			'Denial prevention and appeals',
			'Clinical workflow design',
			'HIPAA aware system design'
		],
		'Technology and AI': [
			'AI agents, prompt design, tool use, evaluation',
			'Python, SQL, TypeScript',
			'Local model inference with LM Studio and Ollama',
			'Process automation',
			'System integration and data migration',
			'Jira, Trello, MS Office Suite, SharePoint'
		]
	};
</script>

<svelte:head>
	<title>Kenny Santanu - Healthcare IT Project Manager</title>
</svelte:head>

<div class="min-h-screen bg-[#1a1d20] text-white antialiased">
	<!-- Header -->
	<header
		class="sticky top-0 z-20 border-b border-[#2c3135] bg-[#1e2124]/95 backdrop-blur supports-[backdrop-filter]:bg-[#1e2124]/80"
	>
		<div class="mx-auto flex max-w-6xl items-center justify-between px-4 py-3 md:px-8">
			<a href="#top" class="flex items-center gap-3">
				<img
					src="{base}/picture.jpg"
					alt="Kenny Santanu"
					class="size-9 rounded-full object-cover"
				/>
				<span class="text-base font-bold tracking-tight">Kenny Santanu</span>
			</a>
			<!-- Desktop nav -->
			<nav class="hidden gap-7 text-sm font-medium text-[#cbd5e1] md:flex">
				{#each navLinks as link}
					<a href={link.href} class="hover:text-white">{link.label}</a>
				{/each}
			</nav>
			<!-- Desktop LinkedIn button -->
			<a
				href="https://www.linkedin.com/in/kennysantanu/"
				target="_blank"
				rel="noopener noreferrer"
				class="hidden items-center gap-2 rounded-full bg-white px-4 py-1.5 text-sm font-semibold text-[#1a1d20] hover:bg-[#e2e8f0] md:inline-flex"
			>
				<Linkedin size={16} />
				LinkedIn
			</a>
			<!-- Mobile hamburger -->
			<button
				class="flex items-center justify-center rounded-lg p-2 text-[#cbd5e1] hover:bg-[#2c3135] hover:text-white md:hidden"
				aria-label="Toggle menu"
				onclick={() => (mobileMenuOpen = !mobileMenuOpen)}
			>
				{#if mobileMenuOpen}
					<X size={22} />
				{:else}
					<Menu size={22} />
				{/if}
			</button>
		</div>
		<!-- Mobile menu dropdown -->
		{#if mobileMenuOpen}
			<nav class="border-t border-[#2c3135] bg-[#1e2124] px-4 py-3 md:hidden">
				<ul class="flex flex-col gap-1">
					{#each navLinks as link}
						<li>
							<a
								href={link.href}
								class="block rounded-lg px-3 py-2.5 text-sm font-medium text-[#cbd5e1] hover:bg-[#2c3135] hover:text-white"
								onclick={() => (mobileMenuOpen = false)}
							>
								{link.label}
							</a>
						</li>
					{/each}
					<li class="pt-2">
						<a
							href="https://www.linkedin.com/in/kennysantanu/"
							target="_blank"
							rel="noopener noreferrer"
							class="flex items-center gap-2 rounded-lg px-3 py-2.5 text-sm font-medium text-[#7dd3fc] hover:bg-[#2c3135]"
							onclick={() => (mobileMenuOpen = false)}
						>
							<Linkedin size={16} />
							LinkedIn
						</a>
					</li>
				</ul>
			</nav>
		{/if}
	</header>

	<main id="top" class="mx-auto max-w-6xl px-4 md:px-8">
		<!-- Hero -->
		<section class="grid gap-8 py-14 md:grid-cols-[auto_1fr] md:items-center md:gap-12 md:py-20">
			<div
				class="aspect-square w-40 self-center rounded-full bg-cover bg-center shadow-xl ring-4 ring-[#2c3135] md:w-56"
				style="background-image: url('{base}/picture.jpg');"
			></div>
			<div>
				<div class="mb-3 flex flex-col gap-1 text-sm text-[#94a3b8] min-[425px]:flex-row min-[425px]:items-center min-[425px]:gap-2">
					<div class="flex items-center gap-2">
						<MapPin size={14} />
						<span>Los Angeles, CA</span>
					</div>
					<span class="hidden min-[425px]:inline mx-2 text-[#475569]">•</span>
					<span>Open to remote and hybrid roles</span>
				</div>
				<h1 class="text-4xl leading-tight font-extrabold tracking-tight md:text-5xl">
					Kenny Santanu
				</h1>
				<p class="mt-1 text-xl font-semibold text-[#7dd3fc] md:text-2xl">
					Healthcare IT Project Manager <span class="text-[#475569]">|</span> PMP
				</p>
				<p class="mt-4 max-w-2xl text-lg text-[#cbd5e1] md:text-xl">
					I turn broken clinical and revenue cycle workflows into systems that work. Eight years
					inside a working clinic, building, shipping, and training people on the result.
				</p>
				<p class="mt-4 max-w-2xl text-base text-[#94a3b8]">
					Tell me your problem. I will find the technology and build the solution.
				</p>
				<div class="mt-7 flex flex-wrap gap-3">
					<a
						href="https://www.linkedin.com/in/kennysantanu/"
						target="_blank"
						rel="noopener noreferrer"
						class="inline-flex items-center gap-2 rounded-full bg-[#2c3135] px-5 py-2.5 text-sm font-bold text-white hover:bg-[#3a4147]"
					>
						<Linkedin size={16} />
						LinkedIn
					</a>
					<a
						href="https://github.com/kennysantanu"
						target="_blank"
						rel="noopener noreferrer"
						class="inline-flex items-center gap-2 rounded-full bg-[#2c3135] px-5 py-2.5 text-sm font-bold text-white hover:bg-[#3a4147]"
					>
						<Github size={16} />
						GitHub
					</a>
				</div>
			</div>
		</section>

		<!-- Impact strip -->
		<section class="mb-16 grid gap-3 rounded-2xl border border-[#2c3135] bg-[#1e2124] p-6 md:grid-cols-4 md:p-8">
			{#each impact as item}
				<div class="flex flex-col">
					<div class="text-3xl font-extrabold tracking-tight text-[#7dd3fc] md:text-4xl">
						{item.value}
					</div>
					<div class="mt-1 text-sm text-[#cbd5e1]">{item.label}</div>
				</div>
			{/each}
		</section>

		<!-- About -->
		<section id="about" class="mb-20 scroll-mt-20 grid gap-8 md:grid-cols-[1fr_2fr]">
			<div>
				<div class="flex items-center gap-2 text-sm font-bold tracking-wider text-[#7dd3fc] uppercase">
					<Sparkles size={16} />
					About
				</div>
				<h2 class="mt-2 text-3xl font-bold tracking-tight">Operations first, technology second.</h2>
			</div>
			<div class="space-y-4 text-[#cbd5e1]">
				<p>
					I am a PMP certified project manager with eight years inside a single private nephrology
					clinic in Los Angeles. That focused environment let me run revenue cycle operations,
					lead an emergency EHR migration, and design an AI powered denial tracker that recovered
					real money for the practice. I learned to manage projects by managing them, not just by
					reading about them.
				</p>
				<p>
					My background blends healthcare operations with a working knowledge of software, data,
					and AI. I hold a Master of Science in Information Technology Management and a Bachelor of
					Science in Computer Science. I run AI agents in production for both clinical and personal
					work, and I write about what actually breaks when AI hits real workflows.
				</p>
				<p>
					Today I am stepping into larger healthcare IT and EHR implementation roles, with a clear
					path toward Functional IT Manager. I am particularly drawn to organizations that sponsor
					Epic or Oracle Health certifications and to teams running clinical AI programs.
				</p>
			</div>
		</section>

		<!-- Credentials -->
		<section class="mb-20">
			<div class="mb-6 flex items-center gap-2 text-sm font-bold tracking-wider text-[#7dd3fc] uppercase">
				<Award size={16} />
				Credentials
			</div>
			<div class="grid gap-3 sm:grid-cols-2 lg:grid-cols-4">
				{#each credentials as cred}
					<div class="rounded-xl border border-[#2c3135] bg-[#1e2124] p-5">
						<div class="text-2xl font-extrabold text-white">{cred.title}</div>
						<div class="mt-1 text-sm font-semibold text-[#cbd5e1]">{cred.subtitle}</div>
						<div class="mt-2 flex items-start gap-2 text-xs text-[#94a3b8]">
							<GraduationCap size={14} class="mt-0.5 shrink-0" />
							<span>{cred.org}</span>
						</div>
					</div>
				{/each}
			</div>
		</section>

		<!-- Experience -->
		<section id="experience" class="mb-20 scroll-mt-20">
			<div class="mb-6 flex items-center gap-2 text-sm font-bold tracking-wider text-[#7dd3fc] uppercase">
				<Briefcase size={16} />
				Experience
			</div>
			<div class="space-y-6">
				{#each experience as job}
					<article class="rounded-2xl border border-[#2c3135] bg-[#1e2124] p-6 md:p-8">
						<div class="flex flex-wrap items-baseline justify-between gap-2">
							<div>
								<h3 class="text-xl font-bold text-white">{job.role}</h3>
								<div class="mt-1 text-sm text-[#cbd5e1]">
									<span class="font-semibold">{job.org}</span>
									<span class="mx-2 text-[#475569]">•</span>
									<span>{job.location}</span>
								</div>
							</div>
							<div class="text-sm text-[#94a3b8]">{job.period}</div>
						</div>
						<ul class="mt-4 space-y-2 text-[#cbd5e1]">
							{#each job.bullets as bullet}
								<li class="flex gap-3">
									<ArrowRight size={16} class="mt-1 shrink-0 text-[#7dd3fc]" />
									<span>{bullet}</span>
								</li>
							{/each}
						</ul>
					</article>
				{/each}
			</div>
		</section>

		<!-- Projects -->
		<section id="projects" class="mb-20 scroll-mt-20">
			<div class="mb-6 flex items-center gap-2 text-sm font-bold tracking-wider text-[#7dd3fc] uppercase">
				<Wrench size={16} />
				Projects
			</div>
			<div class="grid gap-5 md:grid-cols-2">
				{#each projects as project}
					<article class="flex flex-col overflow-hidden rounded-2xl border border-[#2c3135] bg-[#1e2124]">
						{#if project.image}
							<div
								class="aspect-video w-full bg-cover bg-center"
								style="background-image: url('{base}/{project.image}');"
							></div>
						{:else}
							<div
								class="flex aspect-video w-full items-center justify-center bg-gradient-to-br from-[#0c4a6e] via-[#1e2124] to-[#1e2124]"
							>
								<span class="text-sm font-semibold tracking-wider text-[#7dd3fc] uppercase">
									Case Study
								</span>
							</div>
						{/if}
						<div class="flex flex-1 flex-col gap-3 p-6">
							<h3 class="text-lg font-bold text-white">{project.title}</h3>
							<div
								class="flex items-start gap-2 rounded-lg bg-[#0c4a6e]/40 p-3 text-sm font-semibold text-[#7dd3fc]"
							>
								<Quote size={16} class="mt-0.5 shrink-0" />
								<span>{project.outcome}</span>
							</div>
							<p class="text-sm text-[#cbd5e1]">{project.description}</p>
							<p class="text-xs text-[#94a3b8]"><span class="font-semibold text-[#cbd5e1]">My role.</span> {project.role}</p>
							<div class="mt-auto flex flex-wrap gap-2 pt-2">
								{#each project.tech as tag}
									<span
										class="rounded-full border border-[#2c3135] bg-[#15181b] px-3 py-1 text-xs font-medium text-[#cbd5e1]"
									>
										{tag}
									</span>
								{/each}
							</div>
						</div>
					</article>
				{/each}
			</div>
		</section>

		<!-- Skills -->
		<section id="skills" class="mb-20 scroll-mt-20">
			<div class="mb-6 flex items-center gap-2 text-sm font-bold tracking-wider text-[#7dd3fc] uppercase">
				<Sparkles size={16} />
				Skills
			</div>
			<div class="grid gap-5 md:grid-cols-3">
				{#each Object.entries(skills) as [category, items]}
					<div class="rounded-2xl border border-[#2c3135] bg-[#1e2124] p-6">
						<h3 class="mb-3 text-base font-bold text-white">{category}</h3>
						<ul class="space-y-2 text-sm text-[#cbd5e1]">
							{#each items as item}
								<li class="flex gap-2">
									<span class="mt-1 size-1.5 shrink-0 rounded-full bg-[#7dd3fc]"></span>
									<span>{item}</span>
								</li>
							{/each}
						</ul>
					</div>
				{/each}
			</div>
		</section>

		<!-- Contact -->
		<section id="contact" class="mb-20 scroll-mt-20">
			<div
				class="rounded-3xl border border-[#2c3135] bg-gradient-to-br from-[#0c4a6e]/40 via-[#1e2124] to-[#1e2124] p-8 md:p-12"
			>
				<h2 class="text-3xl font-bold tracking-tight md:text-4xl">Have a problem worth solving?</h2>
				<p class="mt-3 max-w-2xl text-[#cbd5e1]">
					I am open to mid level project manager and implementation roles in healthcare IT,
					revenue cycle, EHR, and clinical AI. Remote, hybrid in the Los Angeles area, or contract.
				</p>
				<div class="mt-6 flex flex-wrap gap-3">
					<a
						href="https://www.linkedin.com/in/kennysantanu/"
						target="_blank"
						rel="noopener noreferrer"
						class="inline-flex items-center gap-2 rounded-full bg-[#7dd3fc] px-5 py-2.5 text-sm font-bold text-[#0c4a6e] hover:bg-[#bae6fd]"
					>
						<Linkedin size={16} />
						Message me on LinkedIn
					</a>
					<a
						href="https://github.com/kennysantanu"
						target="_blank"
						rel="noopener noreferrer"
						class="inline-flex items-center gap-2 rounded-full bg-[#2c3135] px-5 py-2.5 text-sm font-bold text-white hover:bg-[#3a4147]"
					>
						<Github size={16} />
						See work on GitHub
					</a>
				</div>
			</div>
		</section>
	</main>

	<footer class="border-t border-[#2c3135]">
		<div class="mx-auto flex max-w-6xl flex-col items-center justify-between gap-2 px-4 py-6 text-xs text-[#94a3b8] md:flex-row md:px-8">
			<span>© 2026 Kenny Santanu. Built with SvelteKit and Tailwind CSS.</span>
			<span>Los Angeles, CA</span>
		</div>
	</footer>
</div>
