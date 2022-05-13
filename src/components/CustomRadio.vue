<template>
	<div>
		<label>
			<input
				type="radio"
				:value="data.value"
				:name="data.name"
				:disabled="data.disabled"
				:class="{ ...data.class }"
				:style="data.style"
				v-model="input"
				class=""
			/>
			<span>{{ data.value }}</span>
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
