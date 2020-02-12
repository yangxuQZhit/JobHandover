# CalibrationBean源码解析

> 用于存储标定设置数据，符合JavaBean模型

#### 属性

```java
private int request;//请求
private int board;//标定板样式
private String cameraType;//相机类型
private String imagePath;//拍照图片存储路径
private MeasureData measureData;//测量数据AB,BC,DS
private int mode;//自动/手动
private List<CalibrationPoint> calibrationPoints;//标定点数据
private List<CalibrationPoint> mPointData;//每个小圆点的最后的坐标，未经准换
```

#### 内部类CalibrationPoint

```java
String fileName;//拍照图片名称
List<Point> points;//数据
```

#### 内部类Point

```java
float x;//横坐标
float y;//纵坐标
boolean isConfirm;//确认标志
```

#### 内部类MeasureData

```java
int AB;
int BC;
int DS;
```