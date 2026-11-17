# Ultraman Shoot (高斯奥特曼 · 3D 体素空战)

> 基于 **Three.js + WebGL GLSL 原生着色器** 的 3D 体素切片（Sprite Stacking）宇宙飞行射击与怪兽空战游戏。
> 纯静态单文件架构，免构建、免依赖、跨端流畅运行。

🔗 **代码仓库**：[https://github.com/studioj2y/ultraman-shoot](https://github.com/studioj2y/ultraman-shoot)  
🌐 **在线试玩预览**：[https://studioj2y.github.io/ultraman-shoot/](https://studioj2y.github.io/ultraman-shoot/)

---

## 核心特性

### 1. 电影级门脸标题画面与自动演示巡航（Attract Mode）
- **特摄金属拉丝 LOGO**：仿射倾斜与无损内边距自适应排版，点缀发光彩色计时器晶核徽标，支持任意屏幕比例。
- **三幕电影级 3D 自动演示**：
  1. **奥特曼特写全向剖析**：镜头 360° 环绕奥特曼旋转，展示 14 层体素结构细节与呼吸微动；
  2. **深空空战巡航演练**：高速掠过带光环气态巨行星，展示动态跟拍、八分光轮发射与体素剥离；
  3. **混沌霸主 Boss 危机**：暗红星云低角仰拍展现 18 层暗黑战兽展开巨翼长角与发光弹幕。
- **即刻出击**：按任意键盘键、鼠标点击或手柄按 (A) / START 即可平滑进入空战，顶栏支持随时一键退回观赏演示。

### 2. 纯正体素硬边与抗跳突渲染（Post-FX & Anti-Aliasing）
- **亚像素抗锯齿像素网格平滑（Subpixel AA）**：过渡带严格收窄至 0.35 物理像素，95% 以上区域保持 100% 锐利的复古方块像素硬边，在极微观边缘消除摄像机运动时的像素跳突（Pixel Crawl）。
- **Karis 软拐点抗闪烁 Bloom**：引入 3A 引擎同款 Karis Average 加权与二次软拐点阈值，消除高光反光微元的跳跃频闪。
- **4x4 Bayer 空间有序抖动（Ordered Dithering）**：分散色阶断层，使深空星云与暗角过渡如复古特摄胶片般均匀细腻。
- **光学衍射十字星芒（Diffraction Spikes）**：模拟镜头光圈叶片衍射，在高能核心产生细小精致的科幻高光星芒。
- **高斯点扩散连续星空**：杜绝离散网格量化，相机无论如何旋转星光皆柔顺平滑。

### 3. 空战打击感与粒子物理
- **体素碎块剥离（Peeling Voxel Debris）**：击中怪兽与 Boss 时，碰撞点向外炸裂飞溅出受力旋转并受重力影响的同色体素碎片。
- **受击微顿帧（Hit-stop）与强化震屏**：致命一击或命中 Boss 时触发短暂停顿与剧烈屏幕震荡，增强打击肉感。
- **波次关卡与多阶段 Boss 战**：击破普通怪兽后触发深空警报与 Boss 降临。Boss 拥有独立血条与混沌弹幕，并在二阶段开启狂暴极速冲撞（Warp Charge）。

### 4. 全平台操作支持
- **键鼠**：
  - 鼠标移动 / `WASD`：空间俯仰与转向
  - 鼠标左键（单击）：**螺旋翻滚闪避（Barrel Roll）** / 键盘 `R`
  - 鼠标左键（按住）：**超光速推进（Boost）** / 键盘 `Shift`
  - 鼠标右键（点击或长按）：**连续发射八分光轮（Ultra Slash）** / 键盘 `C`
  - 鼠标中键 / `M`：**发射斯派修姆高能齐射**
  - `Space`：追尾 / 俯视 / 第一人称视角切换
  - `E`：光球变身与紧急脱离
- **原生手柄（Gamepad API）**：
  - 支持 Xbox / PlayStation / 通用蓝牙手柄即插即用。
  - 左摇杆转向、`RT`/`A` 加速、`RB`/`X` 八分光轮、`Y` 斯派修姆光线、`B` 翻滚闪避、`LB` 筋斗翻越。
  - 支持双马达真实触觉振动反馈（Haptic Rumble）。
- **移动端触控**：
  - 左下角自适应半透明**虚拟操纵摇杆（Virtual Joystick）**。
  - 右侧大触控圆盘（超大光轮、推进、翻滚闪避、大招），防止误触。

---

## 本地运行

纯单文件静态架构，无需 Node.js 或构建步骤：
```bash
# Python 快速启动静态服务
python -m http.server 8080

# 或使用任意静态服务器 (如 npx serve)
npx serve .
```
浏览器打开 `http://localhost:8080` 即可畅玩。

---

## GitHub Pages 部署设置

本项目已内置 `.github/workflows/deploy.yml` 自动化部署流水线：

1. 将代码推送到 GitHub 仓库的 `main` 分支。
2. 在 GitHub 仓库进入 **Settings -> Pages**。
3. 在 **Build and deployment** 下方的 **Source** 下拉菜单中，选择 **GitHub Actions**。
4. GitHub Actions 将自动构建并发布静态页面至：
   **`https://studioj2y.github.io/ultraman-shoot/`**
