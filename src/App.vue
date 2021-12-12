<template>
	<div class="min-h-screen bg-purple-600 text-gray-900">
		<div class="container mx-auto p-4">
			<h2 class="font-bold py-6">Menu (Dropdown)</h2>
			<Menu>
				<MenuButton
					class="flex items-center justify-between px-3 py-2 bg-black bg-opacity-30 text-white rounded-md"
				>
					<span>Options</span>
					<ChevronDownIcon class="h-5 w-5 text-white ml-2" />
				</MenuButton>
				<transition
					enter-active-class="transition duration-100 ease-out"
					enter-from-class="transform scale-75 opacity-0"
					enter-to-class="transform scale-100 opacity-100"
					leave-active-class="transition duration-75 ease-out"
					leave-from-class="transform scale-100 opacity-100"
					leave-to-class="transform scale-75 opacity-0"
				>
					<MenuItems
						class="
							bg-white
							shadow-lg
							rounded-md
							py-3
							px-2
							inline-flex
							flex-col
							mt-2
							focus:outline-none
							w-60
							origin-top-left
						"
					>
						<MenuItem v-slot="{ active }">
							<button
								class="px-2 rounded-md py-2 inline-flex items-center"
								:class="{ 'bg-purple-600 text-white': active }"
							>
								<PencilIcon class="h-5 w-5 text-purple-400" />
								<span class="ml-2">Edit</span>
							</button>
						</MenuItem>

						<MenuItem v-slot="{ active }">
							<button
								class="px-2 rounded-md py-2 inline-flex items-center"
								:class="{ 'bg-purple-600 text-white': active }"
							>
								<DuplicateIcon class="h-5 w-5 text-purple-400" />
								<span class="ml-2">Duplicate</span>
							</button>
						</MenuItem>

						<MenuItem v-slot="{ active }">
							<button
								class="px-2 rounded-md py-2 inline-flex items-center"
								:class="{ 'bg-purple-600 text-white': active }"
							>
								<ArchiveIcon class="h-5 w-5 text-purple-400" />
								<span class="ml-2">Archive</span>
							</button>
						</MenuItem>

						<MenuItem v-slot="{ active, disabled }" :disabled="{ disabled }">
							<button
								class="px-2 rounded-md py-2 inline-flex items-center"
								:class="{
									'bg-purple-600 text-white': active,
									'opacity-50 cursor-not-allowed': disabled,
								}"
							>
								<ExternalLinkIcon class="h-5 w-5 text-purple-400" />
								<span class="ml-2">Move</span>
							</button>
						</MenuItem>

						<MenuItem v-slot="{ active }">
							<button
								class="px-2 rounded-md py-2 inline-flex items-center"
								:class="{ 'bg-purple-600 text-white': active }"
							>
								<TrashIcon class="h-5 w-5 text-purple-400" />
								<span class="ml-2">Delete</span>
							</button>
						</MenuItem>
					</MenuItems>
				</transition>
			</Menu>
		</div>
	</div>
</template>

<script>
	import { Menu, MenuButton, MenuItems, MenuItem } from "@headlessui/vue";
	import {
		ChevronDownIcon,
		PencilIcon,
		DuplicateIcon,
		ArchiveIcon,
		ExternalLinkIcon,
		TrashIcon,
	} from "@heroicons/vue/outline";
	export default {
		components: {
			Menu,
			MenuButton,
			MenuItems,
			MenuItem,
			ChevronDownIcon,
			PencilIcon,
			DuplicateIcon,
			ArchiveIcon,
			ExternalLinkIcon,
			TrashIcon,
		},
	};
</script>