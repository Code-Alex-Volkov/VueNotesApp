<template>
  <!-- note list -->
  <div class="notes">
    <div class="note" :class="{ full: !grid }" v-for="(note, index) in notes" :key="index">
      <div class="note-header">
        <p>{{ note.title }}</p>
		  <p style="cursor: pointer;" @click="removeNote(index)"> x </p>
      </div>
      <div class="note-body">
        <p>{{ note.descr }}</p>
        <span>{{ note.date }}</span>
      </div>
    </div>
  </div>
</template>

<script>
export default {
	props: {
		notes: {
			type: Array,
			required: true
		},
		grid: {
			type: Boolean,
			required: true
		}
	},
	methods: {
		removeNote(index) {
			console.log(`Note id - ${index} remove`)
			this.$emit('remove', index)
		}
	}
}
</script>

<style lang="scss">
.notes {
  display: flex;
  align-items: center;
  justify-content: space-between;
  flex-wrap: wrap;
  padding: 40px 0;
}
.note {
  width: 48%;
  padding: 18px 20px;
  margin-bottom: 20px;
  background-color: #fff;
  transition: all 0.3s cubic-bezier(0.02, 0.01, 0.47, 1);
  box-shadow: 0 15px 20px rgba(0,0,0,0.2);
  &.full {
     width: 100%;
  }
  &:hover {
     box-shadow: 0 15px 20px rgba(0,0,0,0.4);
     transform: translate(0, -6px);
     transition-delay: 0s !important;
  }
}
.note-header {
  display: flex;
  align-items: center;
  justify-content: space-between;
  h1 {
    font-size: 21px;
  }
  p {
    color: #402caf;
  }
  svg {
    margin-right: 12px;
    color: #999;
    cursor: pointer;
    &:last-child {
      margin-right: 0;
    }
    &.active {
      color: #402caf;
    }
  }
}
.note-body {
  p {
    padding: 20px 0;
  }
  span {
    font-size: 14px;
    color: #999;
  }
}
</style>