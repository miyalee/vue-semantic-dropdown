<template>
    <div id="app">
        <div class="ui segment">
            <div class="ui form check">
                <div class="inline field">
                    <label>自定义字段别名：</label>
                    <Dropdown addClass="selection" name="selection" defaultText="请选择"
                              v-model="selectedValue" :options="options"
                              textFiled="value" valueFiled="id"
                              @dropdown-selected="(text) => { selectedText = text}"
                    ></Dropdown>
                    <span>id: {{ selectedValue }} name：{{ selectedText }} </span>
                </div>

                <div class="inline field">
                    <label>只有value字段：</label>
                    <Dropdown addClass="selection" name="selection" defaultText="请选择"
                              v-model="selectedDate" :options="optionList"
                    ></Dropdown>
                    <span>选中：{{ selectedDate }}</span>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: 'app',
    data() {
        return {
            options: [
                {
                    id: 'litteRed',
                    value: '小红'
                },
                {
                    id: 'litteBlue',
                    value: '小蓝'
                }
            ],
            selectedValue: null,
            selectedText: null,

            optionList: [
                '2017-10-1',
                '2017-11-1',
                '2017-12-1'
            ],
            selectedDate: null
        }
    }
}
</script>
