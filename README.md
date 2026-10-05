# Hi, I'm 钟泓鑫

电子科学与技术本科生，专注**嵌入式软件开发**：从 MCU 实时控制到嵌入式 Linux 音视频，
习惯把「能跑通」和「能说清为什么这么设计」当成两件必须同时交付的事。

- 🎓 广东工业大学 · 电子科学与技术（本科）
- 🔧 方向：嵌入式 Linux / 实时控制 / 边缘视觉
- 🌱 最近在做：RV1106 上的音视频边缘网关（V4L2 → 硬件 H.264 → RTSP）

---

## 项目

### 🎥 RV1106 嵌入式 Linux 音视频边缘网关
在 Luckfox Pico Pro/Max（Rockchip RV1106G）上**不依赖官方 rkipc 黑盒程序**，
从零重建整条链路：

```
SC3336 → MIPI CSI → RKISP → V4L2 采集 → 硬件 H.264 编码 → RTSP over TCP
```

自研 RTSP 服务端（协议解析 + SDP + RTP 打包含 FU-A 分片）、有界 Packet Queue
与 Frame RingBuffer 两级缓冲、软件位翻转 I²C 驱动 MPU6500 做 OSD 遥测叠加。
实测 1280×720 @ 30.00 fps，8 小时长稳 864,001 帧零丢帧零泄漏。

`C` `嵌入式 Linux` `V4L2` `Rockchip MPP` `H.264` `RTSP/RTP` `MPU6050` `OSD`

→ [rv1106-edge-gateway](https://github.com/xxbdl-2006/rv1106-edge-gateway)

---

### 🤖 2026 全国大学生电子设计竞赛 H 题 — 车载平衡滚球运动控制系统
小车沿黑线循迹的同时控制钢球在摆杆上稳定于指定位置。
两级架构：**MaixCAM Pro / K230 边缘视觉** + **TI MSPM0G3507 主控**。

- 边缘端 YOLO11n 钢球检测，INT8 量化后部署（`.kmodel` / `.cvimodel`）
- 自采自标 345 张钢球数据集
- 主控：8 路红外加权质心循迹、差速速度环、滚球串级 PID、BNO08X 前馈
- 成绩：定点停车平均偏差 1.20 cm；动态平衡球位最大误差 0.89 cm

`TI MSPM0G3507` `MaixCAM Pro` `K230` `YOLO11n` `串级 PID` `多任务状态机`

→ [nuedc-h-ball-balance](https://github.com/xxbdl-2006/nuedc-h-ball-balance)

---

### 🎮 STM32F407 + FreeRTOS 的 SPI 彩屏掌上游戏机
自制主机与手柄 PCB，实现《森林冰火人》双人游戏。

- FreeRTOS 多任务架构，SPI 驱动彩屏，帧率稳定 20 FPS
- GUI Guider 设计 UI，消息队列打通输入任务与游戏逻辑
- 二值信号量同步画面刷新，长时间运行无内存泄漏

`STM32F407` `FreeRTOS` `LVGL` `GUI Guider` `SPI` `NRF24L01`

→ [stm32-game-console](https://github.com/xxbdl-2006/stm32-game-console)

---

## 技能

| 领域 | 内容 |
| --- | --- |
| 语言 | C / Python / 汇编（基础） |
| 嵌入式 Linux | Buildroot、V4L2、MPP 硬件编解码、RTSP/RTP、多线程与缓冲设计 |
| MCU 开发 | STM32 (HAL/LL)、TI MSPM0、FreeRTOS、CAN、SPI/I²C/UART |
| 控制 | PID 串级控制、FOC、卡尔曼滤波、姿态解算 |
| 视觉 | OpenCV、YOLO 训练与边缘量化部署（nncase / cvimodel） |
| 工具 | Keil MDK、Code Composer Studio、CMake/Make、Git、AD |

---

## 荣誉

- 全国大学生电子设计竞赛 · 广东省二等奖（2026.8）
- 睿抗机器人开发者大赛 · 协同机械臂赛道全国一等奖（2025.9）
- 睿抗机器人开发者大赛 · 机械臂赛道华南赛区一等奖（2025.6）
- ICAN 创新创业大赛 · 省级三等奖（2025.10）
- 蓝桥杯全国软件和信息技术人才大赛 · 广东省赛区二等奖（2025.4）

---

📫 欢迎交流嵌入式相关的问题。
