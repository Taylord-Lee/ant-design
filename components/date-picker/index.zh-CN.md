---
category: Components
group: 数据录入
title: DatePicker
subtitle: 日期选择框
description: 输入或选择日期的控件。
cover: https://mdn.alipayobjects.com/huamei_7uahnr/afts/img/A*xXA9TJ8BTioAAAAAAAAAAAAADrJ8AQ/original
coverDark: https://mdn.alipayobjects.com/huamei_7uahnr/afts/img/A*3OpRQKcygo8AAAAAAAAAAAAADrJ8AQ/original
demo:
  cols: 2
---

## 何时使用

当用户需要输入一个日期，可以点击标准输入框，弹出日期面板进行选择。

## 代码演示

<!-- prettier-ignore -->
<code src="./demo/basic.tsx">基本</code>
<code src="./demo/range-picker.tsx">范围选择器</code>
<code src="./demo/switchable.tsx">切换不同的选择器</code>
<code src="./demo/format.tsx">日期格式</code>
<code src="./demo/time.tsx">日期时间选择</code>
<code src="./demo/disabled.tsx">禁用</code>
<code src="./demo/disabled-date.tsx">不可选择日期和时间</code>
<code src="./demo/select-in-range.tsx">选择不超过七天的范围</code>
<code src="./demo/preset-ranges.tsx">预设范围</code>
<code src="./demo/extra-footer.tsx">额外的页脚</code>
<code src="./demo/size.tsx">三种大小</code>
<code src="./demo/date-render.tsx">定制日期单元格</code>
<code src="./demo/status.tsx">自定义状态</code>
<code src="./demo/bordered.tsx">无边框</code>
<code src="./demo/placement.tsx">弹出位置</code>
<code src="./demo/mode.tsx" debug>受控面板</code>
<code src="./demo/start-end.tsx" debug>自定义日期范围选择</code>
<code src="./demo/suffix.tsx" debug>后缀图标</code>
<code src="./demo/render-panel.tsx" debug>\_InternalPanelDoNotUseOrYouWillBeFired</code>

## API

日期类组件包括以下五种形式。

- DatePicker
- DatePicker\[picker="month"]
- DatePicker\[picker="week"]
- DatePicker\[picker="year"]
- DatePicker\[picker="quarter"] (4.1.0 新增)
- RangePicker

### 国际化配置

默认配置为 en-US，如果你需要设置其他语言，推荐在入口处使用我们提供的国际化组件，详见：[ConfigProvider 国际化](https://ant.design/components/config-provider-cn/)。

如有特殊需求（仅修改单一组件的语言），请使用 locale 参数，参考：[默认配置](https://github.com/ant-design/ant-design/blob/master/components/date-picker/locale/example.json)。

```jsx
import 'dayjs/locale/zh-cn';
import locale from 'antd/es/date-picker/locale/zh_CN';

<DatePicker locale={locale} />;
```

```jsx
// 默认语言为 en-US，如果你需要设置其他语言，推荐在入口文件全局设置 locale
import dayjs from 'dayjs';
import 'dayjs/locale/zh-cn';
import locale from 'antd/locale/zh_CN';

<ConfigProvider locale={locale}>
  <DatePicker defaultValue={dayjs('2015-01-01', 'YYYY-MM-DD')} />
</ConfigProvider>;
```

### 共同的 API

以下 API 为 DatePicker、 RangePicker 共享的 API。

| 参数 | 说明 | 类型 | 默认值 | 版本 |
| --- | --- | --- | --- | --- |
| allowClear | 是否显示清除按钮 | boolean | true |  |
| autoFocus | 自动获取焦点 | boolean | false |  |
| bordered | 是否有边框 | boolean | true |  |
| className | 选择器 className | string | - |  |
| dateRender | 自定义日期单元格的内容 | function(currentDate: dayjs, today: dayjs) => React.ReactNode | - |  |
| disabled | 禁用 | boolean | false |  |
| disabledDate | 不可选择的日期 | (currentDate: dayjs) => boolean | - |  |
| popupClassName | 额外的弹出日历 className | string | - | 4.23.0 |
| getPopupContainer | 定义浮层的容器，默认为 body 上新建 div | function(trigger) | - |  |
| inputReadOnly | 设置输入框为只读（避免在移动设备上打开虚拟键盘） | boolean | false |  |
| locale | 国际化配置 | object | [默认配置](https://github.com/ant-design/ant-design/blob/master/components/date-picker/locale/example.json) |  |
| mode | 日期面板的状态（[设置后无法选择年份/月份？](/docs/react/faq#当我指定了-datepickerrangepicker-的-mode-属性后点击后无法选择年份月份)） | `time` \| `date` \| `month` \| `year` \| `decade` | - |  |
| nextIcon | 自定义下一个图标 | ReactNode | - | 4.17.0 |
| open | 控制弹层是否展开 | boolean | - |  |
| panelRender | 自定义渲染面板 | (panelNode) => ReactNode | - | 4.5.0 |
| picker | 设置选择器类型 | `date` \| `week` \| `month` \| `quarter` \| `year` | `date` | `quarter`: 4.1.0 |
| placeholder | 输入框提示文字 | string \| \[string, string] | - |  |
| placement | 选择框弹出的位置 | `bottomLeft` `bottomRight` `topLeft` `topRight` | bottomLeft |  |
| popupStyle | 额外的弹出日历样式 | CSSProperties | {} |  |
| prevIcon | 自定义上一个图标 | ReactNode | - | 4.17.0 |
| presets | 预设时间范围快捷选择 | { label: React.ReactNode, value: [dayjs](https://day.js.org/) }[] | - |  |
| size | 输入框大小，`large` 高度为 40px，`small` 为 24px，默认是 32px | `large` \| `middle` \| `small` | - |  |
| status | 设置校验状态 | 'error' \| 'warning' | - | 4.19.0 |
| style | 自定义输入框样式 | CSSProperties | {} |  |
| suffixIcon | 自定义的选择框后缀图标 | ReactNode | - |  |
| superNextIcon | 自定义 `<<` 切换图标 | ReactNode | - | 4.17.0 |
| superPrevIcon | 自定义 `>>` 切换图标 | ReactNode | - | 4.17.0 |
| onOpenChange | 弹出日历和关闭日历的回调 | function(open) | - |  |
| onPanelChange | 日历面板切换的回调 | function(value, mode) | - |  |

### 共同的方法

| 名称    | 描述     | 版本 |
| ------- | -------- | ---- |
| blur()  | 移除焦点 |      |
| focus() | 获取焦点 |      |

### DatePicker

| 参数 | 说明 | 类型 | 默认值 | 版本 |
| --- | --- | --- | --- | --- |
| defaultPickerValue | 默认面板日期 | [dayjs](https://day.js.org/) | - |  |
| defaultValue | 默认日期，如果开始时间或结束时间为 `null` 或者 `undefined`，日期范围将是一个开区间 | [dayjs](https://day.js.org/) | - |  |
| disabledTime | 不可选择的时间 | function(date) | - |  |
| format | 设置日期格式，为数组时支持多格式匹配，展示以第一个为准。配置参考 [dayjs](https://day.js.org/)，支持[自定义格式](#components-date-picker-demo-format) | string \| (value: dayjs) => string \| (string \| (value: dayjs) => string)\[] | `YYYY-MM-DD` |  |
| renderExtraFooter | 在面板中添加额外的页脚 | (mode) => React.ReactNode | - |  |
| showNow | 当设定了 `showTime` 的时候，面板是否显示“此刻”按钮 | boolean | - | 4.4.0 |
| showTime | 增加时间选择功能 | Object \| boolean | [TimePicker Options](/components/time-picker-cn#api) |  |
| showTime.defaultValue | 设置用户选择日期时默认的时分秒，[例子](#components-date-picker-demo-disabled-date) | [dayjs](https://day.js.org/) | dayjs() |  |
| showToday | 是否展示“今天”按钮 | boolean | true |  |
| value | 日期 | [dayjs](https://day.js.org/) | - |  |
| onChange | 时间发生变化的回调 | function(date: dayjs, dateString: string) | - |  |
| onOk | 点击确定按钮的回调 | function() | - |  |
| onPanelChange | 日期面板变化时的回调 | function(value, mode) | - |  |

### DatePicker\[picker=year]

| 参数 | 说明 | 类型 | 默认值 | 版本 |
| --- | --- | --- | --- | --- |
| defaultPickerValue | 默认面板日期 | [dayjs](https://day.js.org/) | - |  |
| defaultValue | 默认日期 | [dayjs](https://day.js.org/) | - |  |
| format | 展示的日期格式，配置参考 [dayjs](https://day.js.org/) | string | `YYYY` |  |
| renderExtraFooter | 在面板中添加额外的页脚 | () => React.ReactNode | - |  |
| value | 日期 | [dayjs](https://day.js.org/) | - |  |
| onChange | 时间发生变化的回调，发生在用户选择时间时 | function(date: dayjs, dateString: string) | - |  |

### DatePicker\[picker=quarter]

`4.1.0` 新增。

| 参数 | 说明 | 类型 | 默认值 | 版本 |
| --- | --- | --- | --- | --- |
| defaultPickerValue | 默认面板日期 | [dayjs](https://day.js.org/) | - |  |
| defaultValue | 默认日期 | [dayjs](https://day.js.org/) | - |  |
| format | 展示的日期格式，配置参考 [dayjs](https://day.js.org/) | string | `YYYY-\QQ` |  |
| renderExtraFooter | 在面板中添加额外的页脚 | () => React.ReactNode | - |  |
| value | 日期 | [dayjs](https://day.js.org/) | - |  |
| onChange | 时间发生变化的回调，发生在用户选择时间时 | function(date: dayjs, dateString: string) | - |  |

### DatePicker\[picker=month]

| 参数 | 说明 | 类型 | 默认值 | 版本 |
| --- | --- | --- | --- | --- |
| defaultPickerValue | 默认面板日期 | [dayjs](https://day.js.org/) | - |  |
| defaultValue | 默认日期 | [dayjs](https://day.js.org/) | - |  |
| format | 展示的日期格式，配置参考 [dayjs](https://day.js.org/) | string | `YYYY-MM` |  |
| monthCellRender | 自定义的月份内容渲染方法 | function(date, locale): ReactNode | - |  |
| renderExtraFooter | 在面板中添加额外的页脚 | () => React.ReactNode | - |  |
| value | 日期 | [dayjs](https://day.js.org/) | - |  |
| onChange | 时间发生变化的回调，发生在用户选择时间时 | function(date: dayjs, dateString: string) | - |  |

### DatePicker\[picker=week]

| 参数 | 说明 | 类型 | 默认值 | 版本 |
| --- | --- | --- | --- | --- |
| defaultPickerValue | 默认面板日期 | [dayjs](https://day.js.org/) | - |  |
| defaultValue | 默认日期 | [dayjs](https://day.js.org/) | - |  |
| format | 展示的日期格式，配置参考 [dayjs](https://day.js.org/) | string | `YYYY-wo` |  |
| renderExtraFooter | 在面板中添加额外的页脚 | (mode) => React.ReactNode | - |  |
| value | 日期 | [dayjs](https://day.js.org/) | - |  |
| onChange | 时间发生变化的回调，发生在用户选择时间时 | function(date: dayjs, dateString: string) | - |  |

### RangePicker

| 参数 | 说明 | 类型 | 默认值 | 版本 |
| --- | --- | --- | --- | --- |
| allowEmpty | 允许起始项部分为空 | \[boolean, boolean] | \[false, false] |  |
| dateRender | 自定义日期单元格的内容。`info` 参数自 4.3.0 添加 | function(currentDate: dayjs, today: dayjs, info: { range: `start` \| `end` }) => React.ReactNode | - |  |
| defaultPickerValue | 默认面板日期 | [dayjs](https://day.js.org/)\[] | - |  |
| defaultValue | 默认日期 | [dayjs](https://day.js.org/)\[] | - |  |
| disabled | 禁用起始项 | \[boolean, boolean] | - |  |
| disabledTime | 不可选择的时间 | function(date: dayjs, partial: `start` \| `end`) | - |  |
| format | 展示的日期格式 | string | `YYYY-MM-DD HH:mm:ss` |  |
| presets | 预设时间范围快捷选择 | { label: React.ReactNode, value: [dayjs](https://day.js.org/)\[] }[] | - |  |
| renderExtraFooter | 在面板中添加额外的页脚 | () => React.ReactNode | - |  |
| separator | 设置分隔符 | React.ReactNode | `<SwapRightOutlined />` |  |
| showTime | 增加时间选择功能 | Object\|boolean | [TimePicker Options](/components/time-picker-cn#api) |  |
| showTime.defaultValue | 设置用户选择日期时默认的时分秒，[例子](#components-date-picker-demo-disabled-date) | [dayjs](https://day.js.org/)\[] | \[dayjs(), dayjs()] |  |
| value | 日期 | [dayjs](https://day.js.org/)\[] | - |  |
| onCalendarChange | 待选日期发生变化的回调。`info` 参数自 4.4.0 添加 | function(dates: \[dayjs, dayjs], dateStrings: \[string, string], info: { range:`start`\|`end` }) | - |  |
| onChange | 日期范围发生变化的回调 | function(dates: \[dayjs, dayjs], dateStrings: \[string, string]) | - |  |

## FAQ

### 当我指定了 DatePicker/RangePicker 的 mode 属性后，点击后无法选择年份/月份？

请参考[常见问答](/docs/react/faq#当我指定了-datepickerrangepicker-的-mode-属性后点击后无法选择年份月份)

### 如何在 DatePicker 中使用自定义日期库（如 Moment.js ）？

请参考[《使用自定义日期库》](/docs/react/use-custom-date-library#datepicker)

### 为什么时间类组件的国际化 locale 设置不生效？

参考 FAQ [为什么时间类组件的国际化 locale 设置不生效？](/docs/react/faq#为什么时间类组件的国际化-locale-设置不生效)。

### 如何修改周的起始日？

请使用正确的[语言包](/docs/react/i18n-cn)（[#5605](https://github.com/ant-design/ant-design/issues/5605)），或者修改 dayjs 的 `locale` 配置：<https://codesandbox.io/s/dayjs-day-of-week-x9tuj2?file=/demo.tsx>

```js
import dayjs from 'dayjs';
import 'dayjs/locale/zh-cn';
import 'dayjs/plugin/updateLocale';

dayjs.updateLocale('zh-cn', {
  weekStart: 0,
});
```

### 为何使用 `panelRender` 时，原来面板无法切换？

当你通过 `panelRender` 动态改变层级结构时，会使得原本的 Panel 被当做新的节点删除并创建。这使得其原本的状态会被重置，保持结构稳定即可。详情请参考 [#27263](https://github.com/ant-design/ant-design/issues/27263)。
