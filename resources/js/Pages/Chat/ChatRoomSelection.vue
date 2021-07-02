<template>
	<div class="grid grid-cols-2">
		<div class="font-bold text-xl">
			{{ selected.name }} Chat
		</div>
		<div>
			<select v-model="selected"
					@change="$emit('roomChange', selected)"
					class="float-right">
				<option v-for="(room, key) in rooms" :key="key" :value="room">{{ room.name }}</option>
			</select>
		</div>
	</div>
</template>
<script>
	export default {
		props: ['rooms', 'currentRoom'],
		data: function() {
			return {
				selected: ''
			}
		},
		created(){
			this.selected = this.currentRoom;
		}
	}
</script>