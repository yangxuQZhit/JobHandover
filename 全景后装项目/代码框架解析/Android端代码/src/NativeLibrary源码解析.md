# NativeLibrary源码解析

> Jni接口类

## 基本接口

| 接口功能说明 | 函数名             |
| ------------ | ------------------ |
| 初始化       | init()             |
| Frame渲染    | onDrawFrame()      |
| 渲染窗口更改 | onSurfaceChanged() |
| 注销         | destroy()          |
| 启动环视     | startAnimation()   |

## 交互接口

| 接口功能说明          | 函数名                          |
| --------------------- | ------------------------------- |
| 设置渲染模式          | setOnDrawFrame()                |
| 设置显示模式（2D/3D） | setDisplayMode()                |
| 设置单视图            | setSingleCameraView()           |
| 设置测试图相机索引    | setSideViewCameraIndex()        |
| 触屏事件（普通）      | onTouchEvent()                  |
| 触屏事件（标定）      | onTouchEventCameraCalibration() |

## 车身数据接口（实车）

| 接口功能说明     | 函数名                  |
| ---------------- | ----------------------- |
| 设置轮速         | setWheelSpeeds()        |
| 设置轮向         | setWheelDirections()    |
| 设置方向盘转角   | setSteeringWheelValue() |
| 设置档位         | setCarGear()            |
| 设置尾灯红光抑制 | setRearLight()          |
| 设置雷达状态     | setRadarStatus()        |
| 设置车门状态     | setDoorStatus()         |
| 设置车灯状态     | setCarLightStatus()     |

## 工程设置接口

| 接口功能说明     | 函数名                     |
| ---------------- | -------------------------- |
| 前轨迹线显示设置 | setDisplayFrontTraceLine() |
| 后轨迹线显示设置 | setDisplayBackTraceLine()  |
| 轨迹线类型设置   | setTraceLineType()         |
| 俯视高度设置     | setPitchHeight()           |
| 视频亮度设置     | setVideoBrightness()       |
| 视频对比度设置   | setVideoContrast()         |
| 视频饱和度设置   | setVideoSaturation()       |

## 测试图设置接口

| 接口功能说明       | 函数名                        |
| ------------------ | ----------------------------- |
| 图像畸变校正设置   | setImageCalibration()         |
| 原图水平偏移设置   | setOriginHorizontalOffset()   |
| 原图垂直偏移设置   | setOriginVerticalOffset()     |
| 原图水平缩放设置   | setOriginHorizontalZoom()     |
| 原图垂直缩放设置   | setOriginVerticalZoom()       |
| 原图旋转角度设置   | setOriginRotationAngle()      |
| 校正图视角缩放设置 | setCalibrationViewScale()     |
| 校正图旋转角度设置 | setCalibrationRotationAngle() |

## 车模设置接口

| 接口功能说明     | 函数名                         |
| ---------------- | ------------------------------ |
| 初始化车模颜色   | initCarModelColor()            |
| 加载其他车模     | loadOtherCars()                |
| 设置车模Mesh     | setupCarModelMeshes()          |
| 车模类型更改     | changeCarModelType()           |
| 车模颜色更改     | changeCarModelColor()          |
| 车模亮度更改     | changeCarModelBrightness()     |
| 车模高光更改     | changeCarModelHighlight()      |
| 车模高光范围更改 | changeCarModelHighlightRange() |

## 盲区设置接口

| 接口功能说明 | 函数名              |
| ------------ | ------------------- |
| 设置前盲区   | setFrontBlindZone() |
| 设置后盲区   | setBackBlindZone()  |
| 设置两侧盲区 | setSideBlindZone()  |

## 车身数据接口（设置）

| 接口功能说明 | 函数名                      |
| ------------ | --------------------------- |
| 设置车长     | setCarLength()              |
| 设置车宽     | setCarWidth()               |
| 设置前轮偏移 | setFrontWheelBase()         |
| 设置后轮偏移 | setRearWheelBase()          |
| 设置水平轮距 | setHorizontalWheelSpacing() |
| 设置垂直轮距 | setVeticalWheelSpacing()    |
| 设置车轮宽度 | setTireWidth()              |
| 设置车轮半径 | setTireRadius()             |

## 标定接口

> 在标定算法集成文档中有说明