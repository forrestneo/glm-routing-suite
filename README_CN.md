# glm-routing-suite：GLM 思维路由套件

[ZCode](https://zcode.z.ai) 插件，移植自 [yjh051108/dsh-routing-suite](https://github.com/yjh051108/dsh-routing-suite)（MIT/Apache-2.0）：**四阶段工作流 + 交付证据门禁 + 分级任务协议（含红队门）+ 软阶段门禁 + spec/react 变体预设**。专为 GLM 会话模型适配。

核心承诺：**默认零注入**（装上不改变任何体验，守上游"未触发=官方原样"铁律），所有能力 opt-in。

## 在 ZCode 里安装

**方式 A —— CDN 市场（任何网络可用，包括 github.com 被屏蔽的环境）：**

插件市场 → 添加 → 添加插件市场 → 粘贴：

```
https://cdn.jsdelivr.net/gh/forrestneo/glm-routing-suite@main/marketplace-cdn.json
```

**方式 B —— 直接添加本仓库：**

```
https://github.com/forrestneo/glm-routing-suite
```

装后：个人 → forrestneo-glm-routing-suite → glm-routing-suite → 安装。

## 能力一览

| 能力 | 入口 | 说明 |
|---|---|---|
| 任务分类 | `scripts/route.py` | 中英双语正则：build/fix/weak（本地毫秒级，零 token） |
| 四阶段工作流 | SKILL 协议 | 了解/对齐→拟合方案→开发→验证，完成信号晋级，工具使用不跳级 |
| 交付门禁 | `scripts/delivery_check.py` | 宣告完成前必过：文件三查 + 8 种证据 + reviewed 视觉 + numeric 提示 |
| 分级任务协议 | `scripts/graded.py` | 七步链：定稿→两级规格化（全必填门控）→审核→打卡（红队门）→终验 |
| 软阶段门禁 | PreToolUse 钩子 | graded 规格阶段扣住 write/edit；状态文件防篡改；连拦 3 次自动降级 |
| 变体预设 | `scripts/suite_mode.py preset` | standard / spec（深思优先）/ react（动手优先）三档提醒风格 |

完整文档见 [plugins/glm-routing-suite/README_CN.md](./plugins/glm-routing-suite/README_CN.md)。

## 实测声明

上游行为学数字（DSH+DeepSeek，P1-P23）仅作设计依据引用，未在本移植复现；GLM-5.3 上的对齐收益经 n=40 开/关对照**未证实**（见插件 README 分级标注）。确定性的部分（状态机 34 项穷举单测、门禁 13 项单测）全部通过。

## 许可

MIT（移植部分）；上游组件许可见 [NOTICE](./plugins/glm-routing-suite/NOTICE)（router-standard=MIT，graded=Apache-2.0 语义移植）。
