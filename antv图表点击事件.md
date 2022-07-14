# antv 图表点击事件

```js
import { Column } from "@ant-design/charts";
const dataList = {
  data: [
    {
      type: "家具家电",
      sales: 38,
    },
    {
      type: "粮油副食",
      sales: 600,
    },
  ],
  data1: [
    {
      type: "家具家电",
      sales: 38,
    },
    {
      type: "粮油副食",
      sales: 52,
    },
    {
      type: "生鲜水果",
      sales: 61,
    },
    {
      type: "美容洗护",
      sales: 145,
    },
  ],
  data2: [
    {
      type: "家具家电",
      sales: 38,
    },
    {
      type: "粮油副食",
      sales: 52,
    },
    {
      type: "生鲜水果",
      sales: 61,
    },
    {
      type: "美容洗护",
      sales: 145,
    },
  ],
};
const charlesConfig = (data: any) => {
  var config = {
    data: data,
    xField: "type",
    yField: "sales",
    loading: false,
    columnWidthRatio: 0.7,
    label: {
      layout: [
        { type: "interval-adjust-position" }, // 数据标签自动调整位置
        { type: "interval-hide-overlap" }, // 数据标签防遮挡
        { type: "adjust-color" }, // 数据标签文颜色自动调整
      ],
    },
    meta: {
      type: { alias: "类别" },
      sales: { alias: "销售额" },
    },
  };
  return config;
};
// 点击图表，只有点击在图表实际位置data才会有数据
const onReadyColumn = (plot: any) => {
  plot.on("plot:click", (...args: any) => {
    const data = args[0].data?.data;
    console.log(data);
  });
};

<ProCard title="流程图表" bordered={false} size="small">
  <Row justify="space-around">
    <Col span="7">
      <Column {...charlesConfig(dataList.data)} />
    </Col>
    <Col span="7">
      <Column {...charlesConfig(dataList.data1)} />
    </Col>
    <Col span="7">
      // 在onReady 中绑定事件
      <Column {...charlesConfig(dataList.data2)} onReady={onReadyColumn} />
    </Col>
  </Row>
</ProCard>;
```
