
# Robotic-3D-Vision-Pipeline
## 🏗️ My Robotics-Vision Ecosystem
- [3D Perception Core](链接1) : 高精度位估计算法  
- [Hand-Eye Calibration](链接2) : 工业级标定方案  
- [Integration Demo](链接3) : 全系统视频演示
![3D Vision](https://img.shields.io/badge/3D_Vision-Expert-blue)
![Robotics](https://img.shields.io/badge/Robotics-Industrial-orange)
![Precision](https://img.shields.io/badge/Precision-0.1mm-brightgreen)
## 🔍 核心关键词  
- 手眼标定(Hand-Eye Calibration)  
- 机器人视觉伺服(Visual Servoing)  
- 工业机器人(Industrial Robotics)  

## 🛠️ 技术栈  
- Tsai-Lenz算法 / 在线标定  
- ROS-Industrial / MoveIt  

## 🎯 适用岗位  
- 机器人感知工程师  
- 自动化系统集成师  

## 🔗 手眼标定与位姿估计的协同优化
1. 标定误差传递分析：相机坐标系→机械臂基坐标系  
   ![](docs/error_propagation.png)  
2. 在线标定补偿：当检测到标定误差>0.5mm时自动触发重标定

Robotic-3D-Vision-Pipeline/
├── 1-Calibration/                # 手眼标定模块
│   ├── chessboard_detection/     # 标定板检测
│   ├── hand_eye_solver/          # AX=XB求解
│   └── industrial_validation/    # 产线验证数据
├── 2-Perception/                 # 3D感知模块
│   ├── yolov8_6d_pose/           # YOLO-6D位姿
│   ├── pointcloud_processing/    # 点云配准
│   └── depth_estimation/         # 单目深度
├── 3-Integration/                # 系统整合
│   ├── realtime_pipeline.py      # 全流程脚本
│   └── error_analysis/           # 精度评估
├── docs/
│   ├── Theory.md                 # 数学推导
│   └── Industrial_Case_Study.pdf # 落地案例
└── media/
    ├── calibration.gif           # 标定过程
    └── grasping_accuracy.mp4     # 抓取演示

    ## 🏭 产线验证数据
| 指标               | 结果       |
|--------------------|-----------|
| 重复定位精度       | ±0.3mm    |
| 动态目标抓取成功率 | 89.7%     |

## 🌟 项目亮点
- **手眼协同**：将手眼标定的 `AX=XB` 求解与YOLO-3D检测结合，实现毫米级抓取精度
- **全栈实现**：覆盖从相机标定→物体识别→运动规划的全流程
- **工业验证**：在UR5e机械臂上实现92%抓取成功率（见`media/grasping_demo.mp4`）

## 📊 系统流程图
![流程图](docs/pipeline_flowchart.png)
