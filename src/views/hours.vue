<template>
    <div class="hours">
        <StyledCard>
            <TableBlock :options="tableOptions" />
        </StyledCard>
    </div>
</template>

<script>
import TableBlock from "@/components/table/TableBlock.vue";
import StyledCard from "@/components/_styled/StyledCard.vue";

export default {
    components: {
        TableBlock,
        StyledCard
    },
    computed: {
        hours() {
            let hours = [];
            for (let i = 0; i < 24; i++) {
                hours.push(
                    `${this.$moment()
                        .hour(i)
                        .format("HH")}:00`
                );
            }
            return hours;
        },
        tbody() {
            return [
                this.hours.map(() => {
                    return {
                        options: {
                            type: "text",
                            inputmode: "numeric",
                            max: 999999
                        }
                    };
                })
            ];
        },
        currentHour() {
            return this.$moment().hour() + 1;
        },
        tableOptions() {
            return {
                headers: this.hours,
                tbody: this.tbody,
                current: this.currentHour,
                component: "Input"
            };
        }
    }
};
</script>

<style lang="scss" scoped>
.hours {
    display: flex;
    justify-content: center;
    align-items: center;
    flex: 1 1 100%;
    padding: 25px;
}
</style>
