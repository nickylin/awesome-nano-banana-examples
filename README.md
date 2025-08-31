# Awesome Gemini-Nano-Banana - 精彩应用案例集

[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg?style=flat-square)](http://makeapullrequest.com)

一个由社区驱动的 Gemini-Nano-Banana 模型应用场景、最佳实践和资源分享的精选列表。

[English](./README.en.md) | 中文

---

`gemini-nano-banana` 是谷歌最新推出的高效图片模型，它在生成质量、速度和理解复杂指令方面表现出色。本项目旨在汇集和展示其实际应用案例，激发更多创意。
![alt text](image.png)

## 目录

- [✨ 画廊 (Showcase)](#-画廊-showcase)
- [🛠️ 如何使用 (How to Use)](#️-如何使用-how-to-use)
  - [API 调用示例](#api-调用示例)
  - [命令行工具](#命令行工具)
- [💡 应用场景 (Application Scenarios)](#-应用场景-application-scenarios)
- [📚 资源 & 工具 (Resources & Tools)](#-资源--工具)
- [🤝 如何贡献 (How to Contribute)](#-如何贡献-how-to-contribute)
- [📜 许可证 (License)](#-许可证-license)

## ✨ 画廊 (Showcase)

*在这里展示一些最惊艳、最有代表性的图片，用强烈的视觉冲击吸引访客。*

| 类别 | 提示语 (Prompt) | 生成结果 (Output) |
| :--- | :--- | :--- |
| **手办模型** | `turn this photo into a character figure. Behind it, place a box with the character’s image printed on it, and a computer showing the Blender modeling process on its screen. In front of the box, add a round plastic base with the character figure standing on it. Make the PVC material look clear, and set the scene indoors if possible.` | ![alt text](image-15.png)![汽车模型](![alt text](image-14.png)) |
| **产品渲染** | `A model is posing and leaning against a pink bmw. She is wearing the following items, the scene is against a light grey background. The green alien is a keychain and it's attached to the pink handbag. The model also has a pink parrot on her shoulder. There is a pug sitting next to her wearing a pink collar and gold headphones.` | ![alt text](image-16.png) ![alt text](image-17.png) |
| **虚实结合** | `what does the red arrow see` | ![alt text](image-18.png) ![alt text](image-19.png)|
| **动作参考** | `make it real` | ![alt text](image-20.png) ![alt text](image-21.png)|


*(更多精彩案例请查看 [Showcase 目录](./showcase/))。*

## 🛠️ 如何使用 (How to Use)

*提供清晰、可直接复制粘贴的代码片段。*

### API 调用示例

假设使用官方 Python 库：

```python
import gemini_nano_banana as gnb

# 配置你的 API 密钥
gnb.api_key = "YOUR_API_KEY"

# 定义你的想法
prompt = "一只发光的机械水母，在赛博朋克城市的雨夜上空游动，霓虹灯光反射，电影感，超高细节"

# 生成图片
try:
    image_url = gnb.generate(
        prompt=prompt,
        style="cinematic",
        resolution="1024x1024"
    )
    print(f"图片已生成: {image_url}")
except Exception as e:
    print(f"发生错误: {e}")
```

### 命令行工具

```bash
# 安装工具
pip install gnb-cli

# 生成图片
gnb-cli generate "一只戴着飞行员护目镜的可爱柯基犬，迪士尼风格" --style disney --output corgi.png
```

## 💡 应用场景 (Application Scenarios)

**1. 场景融合 (Combine photos into new scenes)**
   - **说明**: 将多张独立的照片无缝融合成一个全新的、富有想象力的场景。例如，你可以把朋友的照片和一张月球表面的照片结合，生成一张“朋友在月球漫步”的图片，模型会自动处理光照、阴影和透视，让结果看起来天衣无缝。
   ![alt text](image-1.png) ![alt text](image-2.png)

**2. 描述式修图 (Edit image by describing to it)**
   - **说明**: 用自然语言直接“指挥”模型修改图片。不再需要复杂的P图软件，只需要告诉它“给这个女孩戴上一副墨镜”或者“把天空换成梵高星空的风格”，模型就能理解并执行你的指令。
   ![alt text](image-3.png)![alt text](image-4.png)

**3. AI 视频流 (Nano Banana + Runway Act 2)**
   - **说明**: 这是一个强大的工作流。首先使用 Nano Banana 生成一张高质量的静态图片（例如，一个未来城市的关键帧），然后将其导入 Runway Act 2 等视频生成工具，让这张静态图片动起来，极大地简化了动画和视频的创作流程。
   ![alt text](image-5.png)


**4. 广告概念帧 (Start frames for Ads)**
   - **说明**: 在广告制作初期，快速生成大量不同风格、不同创意的“起始帧”或“概念图”。这能帮助创意团队在几分钟内将想法可视化，进行提案和筛选，极大地提升了效率。
   ![alt text](image-6.png)

**5. 风格迁移 (Move styles from one image to another)**
   - **说明**: 将一张图片的艺术风格（如水彩、油画、赛博朋克）应用到另一张图片的内容上。你可以轻松地把一张普通的街景照片，变成一幅充满艺术感的杰作。
   ![alt text](image-7.png) ![alt text](image-8.png)

**6. 图像内文字修改 (Change text)**
   - **说明**: 智能识别并修改图片中的文字内容。比如，你可以轻松地将一张海报上的“夏季大促”改成“秋季上新”，模型会自动匹配原有的字体、颜色和光照效果。
   ![alt text](image-9.png)

**7. 老照片修复与增强 (Restore or fix old and blurry photos)**
   - **说明**: 修复有划痕、模糊不清或分辨率低的老旧照片。模型能够智能地“脑补”出缺失的细节，提升清晰度，甚至为黑白照片上色，让珍贵的回忆重焕新生。
   ![alt text](image-10.png)

**8. 智能背景替换 (Change image background)**
   - **说明**: 轻松更换任何图片的主体背景。无论是为证件照换底色，还是为产品图生成多样化的展示环境，都可以一键完成，并且边缘处理得非常自然。
![alt text](image-11.png)
**9. 独立动漫创作革命 (A new era of indie anime animators)**
   - **说明**: 为独立动画和漫画创作者赋能。通过生成角色设定、场景原画、关键帧动画等，大大降低了创作门槛和成本，让一个人或一个小团队也能创作出高质量的动漫作品。
![alt text](image-12.png)
**10. 风格一致性创作 (Create new images in the same style from a reference photo)**
    - **说明**: 提供一张参考图片，让模型“学习”它的独特风格（包括画风、色调、笔触等），然后用这种风格生成全新的、不同内容的图片。这对于创作系列插画、游戏资产或保持品牌视觉一致性至关重要。
    ![alt text](image-13.png)

## 📚 资源 & 工具

*链接到所有相关的外部资源。*

- **官方文档**: [Gemini Nano Banana API Documentation](https://example.com/docs)

## 🤝 如何贡献 (How to Contribute)

我们非常欢迎社区的贡献！请参考我们的 [贡献指南](./CONTRIBUTING.md)。

## 📜 许可证 (License)

本项目采用 [MIT License](./LICENSE) 授权。