
<template functional>
	<i18n path="fight.leek_state_x_turns" tag="div" :a="props.a">
		<leek slot="leek" :leek="props.leek" />
		<template v-slot:state>
			<b>{{ parent.$t('effect.state_' + props.value) }}</b>
		</template>
		<template v-slot:turns>
			<b>{{ parent.formatTurns(props.turns) }}</b>
		</template>
	</i18n>
</template>

<script lang="ts">
	import { FightLeek } from '@/model/fight'
	import { Component, Prop, Vue } from 'vue-property-decorator'
	import ActionLeekElement from '../report/action-leek.vue'

	@Component({ components: { leek: ActionLeekElement } })
	export default class EffectAddState extends Vue {
		@Prop() leek!: FightLeek
		@Prop() value!: number
		@Prop() turns!: number
		@Prop() a!: number
	}
</script>
