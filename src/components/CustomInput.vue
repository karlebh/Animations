<template>
	<div>
		<label>
			<input
				:type="data.type"
				:placeholder="data.placeholder"
				:value="data.value"
				:name="data.name"
				:min="data.min"
				:max="data.max"
				:readonly="data.readonly"
				:disabled="data.disabled"
				:class="{
					...data.class,
					error_border: !$v.input.minLength || !$v.input.maxLength,
				}"
				:style="data.style"
				:autocomplete="data.autocomplete"
				v-model="$v.input.$model"
				class=""
			/>

			<div style="margin-top: 0.5rem">
				<small class="primary" v-if="!$v.input.required"
					>Field is required</small
				>
				<small class="error" v-if="!$v.input.minLength"
					>Minimun length is {{ $v.input.$params.minLength.min }}</small
				>
				<small class="error" v-if="!$v.input.maxLength"
					>Maximun length is {{ $v.input.$params.maxLength.max }}</small
				>
			</div>

			<span
				v-if="!['number', 'text', 'submit', 'button'].includes(data.type)"
				>{{ data.value }}</span
			>
		</label>
	</div>
</template>

<script>
	import { required, minLength, maxLength } from "vuelidate/lib/validators"

	export default {
		props: {
			data: Object,
		},

		data() {
			return {
				input: "",
				inputClass: this.data.class,
			}
		},

		validations: {
			input: {
				required,
				minLength: minLength(4),
				maxLength: maxLength(15),
			},
		},
	}
</script>

<style>
	.error_border {
		border: 2px solid red;
	}

	.error {
		color: red;
	}

	.primary {
		color: rgb(7, 7, 168);
	}
	input:focus,
	input:hover {
		background-color: whitesmoke;
		outline: none;
	}

	/*
	div {
		margin-bottom: 1.5rem;
	}

	input {
		border-radius: 0.3rem;
	}

	input:focus,
	input:hover {
		background-color: whitesmoke;
		outline: none;
	}

	input[type="button"],
	input[type="submit"] {
		padding: 0.7rem 0.5rem;
		box-shadow: 0;
	}

	input[type="text"] {
		width: 100%;
		padding: 0.7rem 0.5rem;
	}*/
</style>
