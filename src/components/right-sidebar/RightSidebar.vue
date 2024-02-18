<template>
  <div class="right-sidebar">
    <div class="right-sidebar__tabs">
      <button
        v-for="(tab,i) in tabs"
        :key="i"
        :ref="tab.label"
        class="right-sidebar__tab"
        @click="activeTab = tab.label"
      >
        <span>{{ tab.title }}</span>
      </button>
      <div 
        class="right-sidebar__underline"
        ref="underline"
      ></div>
    </div>
    <div 
      class="tasks"
      v-if="activeTab === 'habits'"
    >
      <div 
        class="task"
        v-for="(habit, i) in habits"
        :key="i"
        :class="habit.class"
      >
        <span>{{ habit.title }}</span>
      </div>
    </div>
    <div 
      class="tasks"
      v-if="activeTab === 'tasks'"
    >
      <task-item
        v-for="(task, i) in tasks"
        :key="i"
        :title='task.title'
      />
    </div>
  </div>
</template>

<script>
import TaskItem from '../tasks/TaskItem.vue'

export default {
  data() {
    return {
      tabs: [
        {
          title: 'Habits',
          label: 'habits',
        },
        {
          title: 'Tasks',
          label: 'tasks',
        },
      ],
      habits: [
        {
          title: '🍱 Lunch',
          class: 'red',
        },
        {
          title: '🧘‍♀ ️Yoga',
          class: 'green',
        },
      ],
      tasks: [
        {
          title: 'Wash dishes',
        },
        {
          title: 'Send final diploma',
        },
      ],
      activeTab: null,
    }     
  },

  mounted() {
    this.activeTab = this.tabs[0].label
  },

  methods: {
  },

  watch: {
    activeTab() {
      this.$refs.underline.style.left = `${this.$refs[this.activeTab][0].offsetLeft}px`
    }
  },
  components: {
    TaskItem,
  },
}
</script>

<style lang="scss">
.right-sidebar {
  width: size(406px);
  height: 100%;
  display: flex;
  flex-direction: column;

  &__tabs {
    padding-top: size(24px);
    display: flex;
    position: relative;
  }

  &__tab {
    @include reset-button;
    padding: size(12px) 0;
    flex-basis: 50%;
    display: flex;
    align-items: center;
    justify-content: center;
  }

  &__underline {
    position: absolute;
    bottom: 0;
    left: 0;
    display: block;
    height: size(3px);
    width: 50%;
    background: linear-gradient(to right, #0AA0DA, #67DEC9);
    transition: .3s;
  }
}

.tasks {
  background-color: $dark-white;
  width: 100%;
  flex-basis: 100%;
  flex-shrink: 1;
  padding: size(34px) size(34px) size(22px) size(34px);
}
</style>