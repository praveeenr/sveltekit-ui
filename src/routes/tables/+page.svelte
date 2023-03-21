<script>
	import {
		Button,
		Select,
		Table,
		TableBody,
		TableBodyCell,
		TableBodyRow,
		TableHead,
		TableHeadCell
	} from 'flowbite-svelte';
	import { Modal, Label, Input, Checkbox } from 'flowbite-svelte';
	import { each } from 'svelte/internal';

	// States
	let showModal = false;
	let selected;
	let colors = [
		{ value: 'red', name: 'Red' },
		{ value: 'blue', name: 'Blue' },
		{ value: 'green', name: 'Green' }
	];

	const handleEdit = () => {
		console.log('Hello world');
		showModal = true;
	};

	let arr = [1];
</script>

{#each arr as a}
	<div>
		<Table hoverable striped={false} shadow>
			<TableHead>
				<TableHeadCell>Product name</TableHeadCell>
				<TableHeadCell>Color</TableHeadCell>
				<TableHeadCell>Category</TableHeadCell>
				<TableHeadCell>Price</TableHeadCell>
				<TableHeadCell>
					<span class="sr-only"> Edit </span>
				</TableHeadCell>
			</TableHead>
			<TableBody class="divide-y">
				<TableBodyRow>
					<TableBodyCell>Apple MacBook Pro 17"</TableBodyCell>
					<TableBodyCell>Sliver</TableBodyCell>
					<TableBodyCell>Laptop</TableBodyCell>
					<TableBodyCell>$2999</TableBodyCell>
					<TableBodyCell>
						<button on:click={handleEdit} class="bg-blue-600 px-2 py-1 rounded-md text-white"
							>Edit</button
						>
					</TableBodyCell>
				</TableBodyRow>
				<TableBodyRow>
					<TableBodyCell>Microsoft Surface Pro</TableBodyCell>
					<TableBodyCell>White</TableBodyCell>
					<TableBodyCell>Laptop PC</TableBodyCell>
					<TableBodyCell>$1999</TableBodyCell>
					<TableBodyCell>
						<a href="/tables" class="font-medium text-blue-600 hover:underline dark:text-blue-500">
							Edit
						</a>
					</TableBodyCell>
				</TableBodyRow>
				<TableBodyRow>
					<TableBodyCell>Magic Mouse 2</TableBodyCell>
					<TableBodyCell>Black</TableBodyCell>
					<TableBodyCell>Accessories</TableBodyCell>
					<TableBodyCell>$99</TableBodyCell>
					<TableBodyCell>
						<a href="/tables" class="font-medium text-blue-600 hover:underline dark:text-blue-500">
							Edit
						</a>
					</TableBodyCell>
				</TableBodyRow>
				<TableBodyRow>
					<TableBodyCell>Google Pixel Phone</TableBodyCell>
					<TableBodyCell>Gray</TableBodyCell>
					<TableBodyCell>Phone</TableBodyCell>
					<TableBodyCell>$799</TableBodyCell>
					<TableBodyCell>
						<a href="/tables" class="font-medium text-blue-600 hover:underline dark:text-blue-500">
							Edit
						</a>
					</TableBodyCell>
				</TableBodyRow>
				<TableBodyRow>
					<TableBodyCell>Apple Watch 5</TableBodyCell>
					<TableBodyCell>Red</TableBodyCell>
					<TableBodyCell>Wearables</TableBodyCell>
					<TableBodyCell>$999</TableBodyCell>
					<TableBodyCell>
						<a href="/tables" class="font-medium text-blue-600 hover:underline dark:text-blue-500">
							Edit
						</a>
					</TableBodyCell>
				</TableBodyRow>
			</TableBody>
		</Table>
	</div>
{/each}

<Modal bind:open={showModal} size="lg" class="w-full">
	<form class="mx-5">
		<h3 class="text-xl font-medium text-gray-900 dark:text-white p-0">Add Item</h3>
		<div class="grid gap-6 mb-6 md:grid-cols-2 mt-4">
			<div>
				<Label for="first_name" class="mb-2">First name</Label>
				<Input type="text" id="first_name" placeholder="John" required />
			</div>
			<div>
				<Label for="last_name" class="mb-2">Last name</Label>
				<Input type="text" id="last_name" placeholder="Doe" required />
			</div>
			<div>
				<Label for="company" class="mb-2">Company</Label>
				<Input type="text" id="company" placeholder="Flowbite" required />
			</div>
			<div>
				<Label for="phone" class="mb-2">Phone number</Label>
				<Input
					type="tel"
					id="phone"
					placeholder="123-45-678"
					pattern="[0-9]{3}-[0-9]{2}-[0-9]{3}"
					required
				/>
			</div>
			<div>
				<Label for="website" class="mb-2">Website URL</Label>
				<Input type="url" id="website" placeholder="flowbite.com" required />
			</div>
			<div>
				<Label for="visitors" class="mb-2">Unique visitors (per month)</Label>
				<Input type="number" id="visitors" placeholder="" required />
			</div>
		</div>
		<div class="mb-6">
			<Label for="email" class="mb-2">Email address</Label>
			<Input type="email" id="email" placeholder="john.doe@company.com" required />
		</div>
		<div class="mb-6">
			<Label for="password" class="mb-2">Password</Label>
			<Input type="password" id="password" placeholder="•••••••••" required />
		</div>
		<div class="mb-6">
			<Label for="confirm_password" class="mb-2">Confirm password</Label>
			<Input type="password" id="confirm_password" placeholder="•••••••••" required />
		</div>
		<Checkbox class="mb-6 space-x-1" required
			>I agree with the <a href="/">terms and conditions</a>.</Checkbox
		>
		<Button type="submit">Submit</Button>
	</form>
</Modal>
