<template>
    <transition name="slide-fade" appear>
        <div>
            <h1 class="mb-3">Console</h1>

            <div>
                <p>
                    Allowed commands:
                    <template v-for="(command, index) in allowedCommandList" :key="command">
                        <code>{{ command }}</code>

                        <!-- No comma at the end -->
                        <span v-if="index !== allowedCommandList.length - 1">, </span>
                    </template>
                </p>
            </div>

            <Terminal class="terminal" :rows="20" mode="mainTerminal" name="console"></Terminal>
        </div>
    </transition>
</template>

<script>

import { allowedCommandList } from "../../../backend/util-common";

export default {
    components: {
    },
    data() {
        return {
            allowedCommandList,
        };
    },
    mounted() {

    },
    methods: {

    }
};
</script>

<style scoped lang="scss">
.terminal {
    height: 410px;
}
</style>
