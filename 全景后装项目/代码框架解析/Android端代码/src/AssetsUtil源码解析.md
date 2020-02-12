# AssetsUtil源码解析

> 静态工具类，将assets目录下文件拷贝到SD卡。

#### 拷贝Assets目录到SD卡目录

```java
public static void copyAssetsToSD(Context context) {
    String sdFolderPath = Utils.getContext().getExternalFilesDir("").getAbsolutePath();
    copyFolderFromAssetsToSD(context, "config", sdFolderPath + "/config");
    copyFolderFromAssetsToSD(context, "resources", sdFolderPath + "/resources");
    copyFolderFromAssetsToSD(context, "shader", sdFolderPath + "/shader");
    copyFolderFromAssetsToSD(context, "carModel", sdFolderPath + "/carModel");
}
```

#### 拷贝文件夹下所有文件

```java
private static void copyFolderFromAssetsToSD(Context mContext, String assetsFolderPath, String sdFolderPath) {
    try {
        String[] fileNames = mContext.getResources().getAssets().list(assetsFolderPath);// 获取assets目录下的所有文件及目录名
        assert fileNames != null;
        if (fileNames.length > 0) {//如果是目录，则新建目录
            File file = new File(sdFolderPath);
            if(! file.exists()){
                file.mkdirs();//如果文件夹不存在，则创建目录
            }
            //递归，将目录下的单个文件复制到目录中
            for (String fileName : fileNames) {
                copyFolderFromAssetsToSD(mContext, assetsFolderPath + "/" + fileName, sdFolderPath + "/" + fileName);
            }
        }else {//如果是文件

            InputStream is = mContext.getResources().getAssets().open(assetsFolderPath);
            FileOutputStream fos = new FileOutputStream(new File(sdFolderPath));
            byte[] buffer = new byte[1024];
            int byteCount = 0;
            while ((byteCount = is.read(buffer)) != -1) {// 循环从输入流读取
                // buffer字节
                fos.write(buffer, 0, byteCount);// 将读取的输入流写入到输出流
            }
            fos.flush();// 刷新缓冲区
            is.close();
            fos.close();
        }
    } catch (Exception e) {
        // TODO Auto-generated catch block
        e.printStackTrace();
    }
}
```