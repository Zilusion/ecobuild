<script lang="ts">
	import { Phone, Mail, MapPin } from 'lucide-svelte';
	let formState: 'idle' | 'submitting' | 'success' | 'error' = $state('idle');
	let name = $state('');
	let email = $state('');
	let message = $state('');

	async function handleSubmit(event: Event) {
		event.preventDefault();

		if (formState === 'submitting') return;

		formState = 'submitting';

		if (!name || !email || !message) {
			formState = 'error';
			return;
		}

		await new Promise((resolve) => setTimeout(resolve, 1500));

		if (Math.random() > 0.1) {
			formState = 'success';
		} else {
			formState = 'error';
		}
	}
</script>

<div class="container mx-auto px-4 py-16 sm:py-24">
	<div class="text-center">
		<h1 class="font-display text-dark-text text-4xl font-bold">Свяжитесь с нами</h1>
		<p class="text-dark-text/70 mx-auto mt-4 max-w-2xl text-lg">
			Мы всегда на связи и готовы ответить на ваши вопросы, обсудить проект или просто пообщаться.
		</p>
	</div>

	<div class="mx-auto mt-16 grid max-w-6xl grid-cols-1 gap-8 lg:grid-cols-12 lg:gap-12">
		<div class="rounded-xl border bg-white p-6 shadow-lg sm:p-8 lg:col-span-7">
			<h2 class="font-display text-dark-text text-2xl font-bold">Отправьте нам сообщение</h2>

			{#if formState === 'success'}
				<div
					class="mt-6 flex flex-col items-center justify-center rounded-md bg-green-50 p-8 text-center"
				>
					<div class="flex h-16 w-16 items-center justify-center rounded-full bg-green-100">
						<svg
							xmlns="http://www.w3.org/2000/svg"
							class="h-10 w-10 text-green-600"
							fill="none"
							viewBox="0 0 24 24"
							stroke="currentColor"
						>
							<path
								stroke-linecap="round"
								stroke-linejoin="round"
								stroke-width="2"
								d="M5 13l4 4L19 7"
							/>
						</svg>
					</div>
					<h3 class="mt-4 text-xl font-semibold text-green-800">Спасибо!</h3>
					<p class="mt-2 text-green-700">
						Ваше сообщение успешно отправлено. Мы свяжемся с вами в ближайшее время.
					</p>
				</div>
			{:else}
				<form onsubmit={handleSubmit} class="mt-6 space-y-6">
					<div>
						<label for="name" class="block text-sm font-semibold text-gray-700">Ваше имя</label>
						<input
							bind:value={name}
							type="text"
							id="name"
							required
							placeholder="Иван Иванов"
							class="focus:border-brand-green focus:ring-brand-green/50 mt-1 block w-full rounded-md border-gray-300 shadow-sm transition focus:ring"
						/>
					</div>
					<div>
						<label for="email" class="block text-sm font-semibold text-gray-700">Email</label>
						<input
							bind:value={email}
							type="email"
							id="email"
							required
							placeholder="you@example.com"
							class="focus:border-brand-green focus:ring-brand-green/50 mt-1 block w-full rounded-md border-gray-300 shadow-sm transition focus:ring"
						/>
					</div>
					<div>
						<label for="message" class="block text-sm font-semibold text-gray-700"
							>Ваше сообщение</label
						>
						<textarea
							bind:value={message}
							id="message"
							rows="5"
							required
							placeholder="Расскажите немного о вашем проекте..."
							class="focus:border-brand-green focus:ring-brand-green/50 mt-1 block w-full rounded-md border-gray-300 shadow-sm transition focus:ring"
						></textarea>
					</div>

					{#if formState === 'error'}
						<p class="text-sm text-red-600">
							Произошла ошибка. Пожалуйста, проверьте все поля и попробуйте снова.
						</p>
					{/if}

					<button
						type="submit"
						disabled={formState === 'submitting'}
						class="bg-brand-green hover:bg-opacity-90 flex w-full items-center justify-center gap-3 rounded-md px-6 py-3 text-lg font-semibold text-white transition active:scale-95 disabled:cursor-not-allowed disabled:bg-gray-400"
					>
						{#if formState === 'submitting'}
							<div
								class="h-5 w-5 animate-spin rounded-full border-2 border-white border-t-transparent"
							></div>
							<span>Отправка...</span>
						{:else}
							<span>Отправить сообщение</span>
						{/if}
					</button>
				</form>
			{/if}
		</div>

		<div class="space-y-8 lg:col-span-5">
			<div class="rounded-xl border bg-white p-6 shadow-lg sm:p-8">
				<h3 class="font-display text-dark-text text-2xl font-bold">Контактная информация</h3>
				<ul class="mt-6 space-y-6">
					<li class="flex items-start">
						<MapPin class="text-brand-green mt-1 h-6 w-6 flex-shrink-0" />
						<div class="ml-4">
							<span class="font-semibold text-gray-800">Наш офис</span>
							<p class="text-gray-600">г. Москва, ул. Зеленая, д. 1, офис 303</p>
						</div>
					</li>
					<li class="flex items-start">
						<Phone class="text-brand-green mt-1 h-6 w-6 flex-shrink-0" />
						<div class="ml-4">
							<span class="font-semibold text-gray-800">Телефон</span>
							<a href="tel:+74951234567" class="hover:text-brand-green block text-gray-600"
								>+7 (495) 123-45-67</a
							>
						</div>
					</li>
					<li class="flex items-start">
						<Mail class="text-brand-green mt-1 h-6 w-6 flex-shrink-0" />
						<div class="ml-4">
							<span class="font-semibold text-gray-800">Электронная почта</span>
							<a href="mailto:hello@ecobuild.dev" class="hover:text-brand-green block text-gray-600"
								>hello@ecobuild.dev</a
							>
						</div>
					</li>
				</ul>
			</div>

			<div class="h-80 overflow-hidden rounded-xl border shadow-lg">
				<iframe
					src="https://yandex.ru/map-widget/v1/?um=constructor%3A3a5a733716a543419574d71587a876a38258e578c772c730877995f57476104e&source=constructor"
					width="100%"
					height="100%"
					frameborder="0"
					title="Карта с нашим расположением"
					loading="lazy"
					class="brightness-110 contrast-100 hue-rotate-180 invert saturate-0"
				></iframe>
			</div>
		</div>
	</div>
</div>
