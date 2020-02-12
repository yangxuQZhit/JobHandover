# AnnotationMacro源码解析

> 注释宏，代替枚举

#### ScreenMode

> 横竖屏模式

| 枚举值     | 含义 |
| ---------- | ---- |
| HORIZONTAL | 水平 |
| VERTICAL   | 垂直 |

#### DisplayMode

> 2D/3D显示模式

| 枚举值 | 含义   |
| ------ | ------ |
| MODE2D | 2D显示 |
| MODE3D | 3D显示 |

#### TextureMode

> 纹理模式

| 枚举值 | 含义               |
| ------ | ------------------ |
| OES    | 纹理来自摄像头数据 |
| PIC    | 纹理来自图片数据   |
| VIDEO  | 纹理来自视频数据   |

#### CameraView

> 相机视图

| 枚举值            | 含义     |
| ----------------- | -------- |
| BACK              | 后视图   |
| FRONT             | 前视图   |
| LEFT              | 左视图   |
| RIGHT             | 右视图   |
| LEFTFRONT         | 左前视图 |
| RIGHTFRONT        | 右前视图 |
| LEFTBACK          | 左后视图 |
| RIGHTBACK         | 右后视图 |
| DOUBLE_VIEW_FRONT | 双前视图 |
| DOUBLE_VIEW_BACK  | 双后视图 |

#### OnDrawFrameMode

> 渲染模式

| 枚举值                | 含义           |
| --------------------- | -------------- |
| MAIN                  | 主视图模式     |
| BASIC                 | 基本设置模式   |
| CARMODEL              | 车模设置模式   |
| PROJECT               | 工程设置模式   |
| CALIBRATION           | 校正设置模式   |
| SIDEVIEW              | 侧视图设置模式 |
| SURROUNDVIEW          | 环视模式       |
| MEDIAPLAYERVIEW       | 播放器模式     |
| BLACKVIEW             | 黑屏模式       |
| MANUALCALIBRATIONVIEW | 手动校准模式   |
| FOURCAMERAVIEW        | 四相机视图模式 |
| BACKCAMERAVIEW        | 后相机视图模式 |
| FRONTCAMERAVIEW       | 前相机视图模式 |
| LEFTCAMERAVIEW        | 左相机视图模式 |
| RIGHTCAMERAVIEW       | 右相机视图模式 |
| BLINDZONE             | 盲区模式       |

#### Gear

> 档位

| 枚举值 | 含义 |
| ------ | ---- |
| FRONT  | 前挡 |
| BACK   | 后档 |
| NONE   | 空档 |

#### Board

> 板子

| 枚举值     | 含义     |
| ---------- | -------- |
| BOARD_T7   | T7板子   |
| BOARD_8953 | 8953板子 |

#### CalibrationMode

> 标定模式

| 枚举值 | 含义     |
| ------ | -------- |
| AUTO   | 自动标定 |
| MANUAL | 手动标定 |

#### CalibrationBoardType

> 标定板样式

| 枚举值 | 含义  |
| ------ | ----- |
| TYPE1  | 样式1 |
| TYPE2  | 样式2 |
| TYPE3  | 样式3 |
| TYPE4  | 样式4 |

#### CameraType

> 相机类型

| 枚举值       | 含义          |
| ------------ | ------------- |
| CAMERA_1002  | 1002型号相机  |
| CAMERA_6047  | 6047型号相机  |
| CAMERA_3308  | 3308型号相机  |
| CAMERA_8255  | 8255型号相机  |
| CAMERA_2706  | 2706型号相机  |
| CAMERA_6007  | 6007型号相机  |
| CAMERA_31006 | 31006型号相机 |
| CAMERA_3011  | 3011型号相机  |
| CAMERA_9013  | 9013型号相机  |

#### CalibrationRequest

> 标定请求

| 枚举值  | 含义     |
| ------- | -------- |
| BEGIN   | 开始请求 |
| END     | 结束请求 |
| INVALID | 为定义   |

#### LabelState

> 标签状态

| 枚举值       | 含义     |
| ------------ | -------- |
| FRONT        | 前视图   |
| BACK         | 后视图   |
| LEFT_2D      | 2D左视图 |
| LEFT_3D      | 3D左视图 |
| RIGHT_2D     | 2D右视图 |
| RIGHT_3D     | 3D右视图 |
| FRONT_DOUBLE | 双前视图 |
| BACK_DOUBLE  | 双后视图 |



