<template>
    <div>
        <div class="tabs">
            <ul>
                <li
                    v-for="(tab, idx) in tabs"
                    :key="idx"
                    :class="{ 'is-active': tab.isActive }"
                >
                    <a
                        :href="tab.href"
                        @click="selectTab(tab)"
                    >
                        {{ tab.name }}
                    </a>
                </li>
            </ul>
        </div>

        <div class="tabs-details">
            <slot></slot>
        </div>
    </div>
</template>


<script>
export default {
    data() {
        return {
            tabs: []
        };
    },
        
    created() {
        
        this.tabs = this.$children;
        
    },

    methods: {
        selectTab(selectedTab) {
            this.tabs.forEach(tab => {
                tab.isActive = (tab.name == selectedTab.name);
            });
        }
    }
}
</script>

<style>
ul {
    display: flex;
    list-style-type: none;
}

li {
    border-radius: 100px;
}

li a {
    display: block;
    text-decoration: none;
    text-transform: uppercase;
    color: #B3A296;
    font-family: Neucha;
    font-size: 28px;
    font-style: normal;
    font-weight: 400;
    line-height: 32px;
    padding: 16px 32px;
}

li:hover,
.is-active {
    background: #000000;
}

li:hover a,
.is-active a {
    color: #ffffff;
}


</style>