<template>
	<div>
		<label>
			<input
				type="checkbox"
				:placeholder="data.placeholder"
				:value="data.value"
				:name="data.name"
				:disabled="data.disabled"
				:class="{ ...data.class }"
				:style="data.style"
				:autocomplete="data.autocomplete"
				v-model="input"
				class=""
			/>
			<span style="margin-left: 0.6rem">{{ data.value }}</span>
		</label>
	</div>
</template>

<script>
	export default {
		props: {
			data: Object,
		},

		data() {
			return {
				input: "",
			}
		},
	}
</script>
