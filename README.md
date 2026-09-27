<div align="center">

# 昔涟 · Cyrene

**陪你写代码的 Q 版桌面小伙伴**

Codex 自定义宠物 · 16 个视线方向 · 悬停微笑挥手 · 透明背景

<img src="assets/previews/idle.gif" width="192" height="208" alt="昔涟待机：轻轻呼吸与眨眼">

[安装](#安装) · [动作预览](#动作预览) · [资源说明](#资源说明) · [MIT License](LICENSE)

</div>

## 动作预览

| 待机 | 鼠标悬停 | 16 个视线方向 |
| :---: | :---: | :---: |
| ![待机](assets/previews/idle.gif) | ![微笑与轻挥手](assets/previews/hover.gif) | ![环绕视线](assets/previews/look-directions.gif) |
| 呼吸、眨眼 | 轻轻微笑、抬手挥动、自然放下 | 抬头、低头、左右侧看与斜向过渡 |

| 向左移动 | 向右移动 |
| :---: | :---: |
| ![向左移动](assets/previews/move-left.gif) | ![向右移动](assets/previews/move-right.gif) |

这是第三版 Q 版造型的微笑挥手修订版。保留粉色长发、玫瑰羽饰与白紫青配色，将细节集中在脸部和轮廓上，方便在桌面宠物的小尺寸下辨认。悬停时双脚保持原位，不再跳跃。

## 安装

需要支持自定义宠物和 v2 图集的 Codex 桌面版本。

### macOS / Linux

下载本仓库 ZIP 并解压，或者克隆仓库：

```sh
git clone https://github.com/TerminusAkivili/codex-pet-cyrene.git
cd codex-pet-cyrene
```

将宠物文件复制到本机 Codex 的 `pets` 目录。下面的命令会先备份已有同名宠物：

```sh
pet_root="${CODEX_HOME:-$HOME/.codex}/pets"
pet_id="cyrene--lingxiaotian"
mkdir -p "$pet_root"
if [ -d "$pet_root/$pet_id" ]; then
  cp -R "$pet_root/$pet_id" "$pet_root/${pet_id}.backup-$(date +%Y%m%d-%H%M%S)"
fi
mkdir -p "$pet_root/$pet_id"
cp "pets/$pet_id/pet.json" "pets/$pet_id/spritesheet.webp" "$pet_root/$pet_id/"
```

### Windows

下载 ZIP 并解压，将 `pets/cyrene--lingxiaotian` 文件夹复制到 `%USERPROFILE%\.codex\pets\`。如果设置了 `CODEX_HOME`，则使用该目录下的 `pets`。覆盖同名目录前先保留备份。

### 显示宠物

在应用设置的 **Pets / 宠物** 中选择“昔涟”，使用 `/pet` 或显示宠物入口唤出。不同应用版本的设置位置可能略有不同。参见 [OpenAI 官方宠物设置说明](https://learn.chatgpt.com/docs/reference/settings#pets)。

若已经安装旧版但画面未更新，重新选择宠物或重启应用后再查看。

## 资源说明

```text
pets/cyrene--lingxiaotian/
├── pet.json          # 名称与图集版本
└── spritesheet.webp  # 透明无损 WebP 动画图集
assets/previews/      # README 的 GIF 预览
LICENSE              # MIT 协议
NOTICE.md            # 素材来源与第三方权利说明
```

| 项目 | 内容 |
| --- | --- |
| 设计版本 | V3，悬停微笑挥手修订版 |
| 图集协议 | `spriteVersionNumber: 2` |
| 图集尺寸 | 1536 × 2288，8 列 × 11 行 |
| 单帧尺寸 | 192 × 208 |
| 基础动作 | 待机、左右移动、挥手、悬停问候、失败反应、等待、思考工作、查看结果 |
| 视线方向 | 16 个，顺时针排列 |

悬停问候使用原 `jumping` 动作槽的 5 帧，表现已改为微笑与小幅挥手。GIF 是预览，实际播放时机和速度由应用控制。低头附近几个中间方向的左右线索较轻，四个主要朝向清楚。

## 制作与检查

素材使用 Codex 内置图像生成工具辅助制作，按动作逐组生成，再进行透明背景处理、切帧与图集组装。已检查尺寸、使用帧、透明背景、主要朝向和动作连续性；最新悬停修改仅替换一个动作槽。

## 许可与致谢

本仓库可授权的原创贡献采用 [MIT License](LICENSE)。角色“昔涟 / Cyrene”来自《崩坏：星穹铁道》，相关角色与商标权利归原权利人；MIT 不授予这些第三方权利。本项目为非官方同人项目。

早期使用过 [legeling](https://github.com/legeling) 的宠物包，其旧元数据标注为 CC BY-NC 4.0。本仓库发布的是重新生成的当前版，不包含该旧图集或原作参考图片，也没有将其旧许可改写为 MIT。详见 [NOTICE.md](NOTICE.md)。
