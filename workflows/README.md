# 工作流

本目录存放 Coze 工作流的导出文件。

## 工作流列表

| 文件名 | 类型 | 用途 |
|--------|------|------|
| `kefu_qing5_12.yaml` | 主流程 | 意图识别 → 分流到子流程/闲聊 |
| `kefu_dingdan_qingqing512.yaml` | 子流程 | 订单查询 |
| `tousu_qing512.yaml` | 子流程 | 客户投诉处理 |
| `tuijian_qing512.yaml` | 子流程 | 商品推荐 |

## 主工作流结构 (kefu_qing5_12)

```
开始(start) → 意图识别(intent)
  ├── branch_0 → 订单查询 (kefu_dingdan_qingqing512)
  ├── branch_1 → 客户投诉 (tousu_qing512)
  ├── branch_2 → 商品推荐 (tuijian_qing512)
  └── default  → 闲聊对话(LLM:豆包1.8深度思考) → 输出 → 结束
```

### 意图识别分类
- 订单查询
- 客户投诉
- 商品推荐
- 其他（走闲聊对话）

## 如何导出工作流

1. 打开 Coze 智能体编辑页面
2. 进入「工作流」标签
3. 点击工作流右侧的「...」→「导出」
4. 将导出的文件放到本目录
