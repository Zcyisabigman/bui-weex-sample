<template>
    <div>
        <bui-header
                title="懒加载(bui-lazy-render)"
                :leftItem="leftItem"
                @leftClick="back">
        </bui-header>

        <div class="center" style="padding: 10px">
            <bui-lazy-render time=1000>
                <bui-panel title="延迟1s出来" type="warning" border="1">
                    <bui-image style="width: 260px;height: 260px;" src="/image/demo.png"></bui-image>
                </bui-panel>
            </bui-lazy-render>

            <bui-lazy-render time=3000 @loaded="onLoad">
                <bui-panel title="延迟3s出来" type="info" border="1">
                    <bui-image style="width: 260px;height: 260px;" src="/image/demo.png"></bui-image>
                </bui-panel>
            </bui-lazy-render>
        </div>
    </div>
</template>

<style lang="sass" src="bui-weex/src/css/buiweex.scss"></style>
<script>
    export default {
        data: function () {
            return {
                leftItem: {
                    icon: 'ion-chevron-left'
                },
            }
        },
        methods: {
            back () {
                this.$pop();
            }
        }
    }
</script>