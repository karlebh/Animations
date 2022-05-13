<template>
	<div>
		<select
			:name="data.name"
			v-model="$v.people.$model"
			:id="data.id"
			:class="{ ...data.class, error_border: $v.people.$anyError }"
			class=""
		>
			<option value="" selected="selected">Select Option</option>
			<option v-for="(item, index) in items" :key="index">
				{{ item.name }}
			</option>
		</select>

		<div style="margin-top: 0.5rem">
			<small
				:class="{ primary: !$v.people.required, error: $v.people.$anyError }"
				v-if="!$v.people.required || $v.people.$anyError"
				>Field is required</small
			>
		</div>
	</div>
</template>

<script>
	import { required } from "vuelidate/lib/validators"

	export default {
		props: ["data"],
		data() {
			return {
				items: this.data.items,
				people: "",
			}
		},

		validations: {
			people: {
				required,
			},
		},
	}
</script>

<style>
/*
	div {
		margin-bottom: 1.5rem;
	}

	select {
		width: 104%;
		box-shadow: rgba(0, 0, 0, 0.05) 0px 6px 24px 0px,
			rgba(0, 0, 0, 0.08) 0px 0px 0px 1px;
		border-radius: 0.3rem;
		border: 1.5px solid;
		outline: none;
		padding: 0.7rem 0.5rem;
	}
*/
	.error {
		color: red;
		font-weight: 600;
	}

	.error_border {
		border: 2px solid red;
		font-weight: 600;
	}
</style>
