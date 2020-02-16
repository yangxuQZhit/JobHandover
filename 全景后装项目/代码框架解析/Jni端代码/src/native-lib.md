# native-lib文件

> 对应Android端的NativeLibrary.java文件

**结构图**

![native-lib结构图](../res/native-lib组件.png)

## 代码解析

#### 全局变量

```c++
StateManager *stateManager = nullptr;//状态管理+标定
MediaPlayerView *mediaPlayerView = nullptr;//录像
ProxyDraw *proxyDraw = nullptr;//绘制代理
```

#### 初始化

```c++
JNIEXPORT void JNICALL
Java_com_byd_aftermarketsvm_NativeLibrary_init(JNIEnv *env, jclass, jstring path, jstring textureMode, jstring board, jint carType) {
    SingletonConfig::createConfig(env->GetStringUTFChars(path, nullptr));
    Factory::create(env->GetStringUTFChars(textureMode, nullptr), env->GetStringUTFChars(board, nullptr));
    proxyDraw = new ProxyDraw(carType);
    stateManager = new StateManager();
    proxyDraw->subscribe(stateManager);
    stateManager->setDraw(proxyDraw->getDraw(0));//drawMain
}
```

