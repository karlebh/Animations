<template>
	<div style="display: flex; justify-content: center">
		<form class="form" style="flex-grow: 1">
			<CustomInput
				:data="{
					name: 'name',
					type: 'text',
					value: 'Cool Value',
					placeholder: 'Enter Your Name',
					class: ['form-input', 'first'],
					autocomplete: 'off',
				}"
			/>


			<div style="display: inline-flex">
				<CustomCheckbox
					:data="{
						name: 'food',
						value: 'Bread',
					}"
					style="margin-right: 10px"
				/>
				<CustomCheckbox
					:data="{
						name: 'food',
						value: 'Fish',
					}"
					style="margin-right: 10px"
				/>
				<CustomCheckbox
					:data="{
						name: 'food',
						value: 'Meat',
					}"
					style="margin-right: 10px"
				/>

				

			</div>

			<CustomSelect :data="{ items: items, name: 'mySelect' }" />

			<div style="display: inline-flex">
				<CustomRadio
					:data="{ name: 'sex', value: 'Male' }"
					style="margin-right: 10px"
				/>

				<CustomRadio
					:data="{
						name: 'sex',
						value: 'Female',
						placeholder: 'Enter Your Name',
						class: 'form-input first',
					}"
				/>
			</div>

			<div style="display: inline-flex">
				<button
					style="
						background-color: gray;
						color: white;
						font-weight: 500;
						padding: 0.7rem 0.5rem;
						border-radius: .3rem
					"
				>
					Submit Form
				</button>
			</div>
		</form>
	</div>
</template>

<script>
	// import { required } from "vuelidate/lib/validators"

	import CustomInput from "./CustomInput"
	import CustomSelect from "./CustomSelect"
	import CustomCheckbox from "./CustomCheckbox"
	import CustomRadio from "./CustomRadio"

	export default {
		props: ["data"],

		data() {
			return {
				items: [
					{ id: 1, name: "John", job: "Developer" },
					{ id: 1, name: "Jane", job: "Nurse" },
				],
			}
		},

		components: {
			CustomInput,
			CustomSelect,
			CustomCheckbox,
			CustomRadio,
		},
	}
</script>

<style scoped>
	.form {
		display: flex;
		flex-direction: column;
		max-width: 600px;
	}
</style>
