# GLES20Util源码解析

> 静态工具类，绑定GL纹理

#### 绑定OES纹理

```java
public static int getOESTexture(int glTexture) {
    int[] texture = new int[1];
    GLES20.glGenTextures(1, texture, 0);
    GLES20.glActiveTexture(glTexture);
    GLES20.glBindTexture(GLES11Ext.GL_TEXTURE_EXTERNAL_OES, texture[0]);
    GLES20.glTexParameterf(GLES11Ext.GL_TEXTURE_EXTERNAL_OES, GL10.GL_TEXTURE_MIN_FILTER, GL10.GL_LINEAR);
    GLES20.glTexParameterf(GLES11Ext.GL_TEXTURE_EXTERNAL_OES, GL10.GL_TEXTURE_MAG_FILTER, GL10.GL_LINEAR);
    GLES20.glTexParameterf(GLES11Ext.GL_TEXTURE_EXTERNAL_OES, GL10.GL_TEXTURE_WRAP_S, GL10.GL_CLAMP_TO_EDGE);
    GLES20.glTexParameterf(GLES11Ext.GL_TEXTURE_EXTERNAL_OES, GL10.GL_TEXTURE_WRAP_T, GL10.GL_CLAMP_TO_EDGE);
    return texture[0];
}
```

#### 绑定PIC纹理

```java
public static int getPICTexture(Context context, String textureFileName, int glTexture) {
    int[] texture = new int[1];
    try{
        InputStream Pic = context.getResources().getAssets().open(textureFileName);
        BitmapFactory.Options op = new BitmapFactory.Options();
        op.inScaled = false;
        Bitmap mbitmap = BitmapFactory.decodeStream(Pic,null,op);

        if(mbitmap!=null && !mbitmap.isRecycled()){
            GLES20.glGenTextures(1,texture,0);
            GLES20.glActiveTexture(glTexture);
            GLES20.glBindTexture(GLES20.GL_TEXTURE_2D,texture[0]);
            GLES20.glTexParameterf(GLES20.GL_TEXTURE_2D, GLES20.GL_TEXTURE_MIN_FILTER,GLES20.GL_NEAREST);
      GLES20.glTexParameterf(GLES20.GL_TEXTURE_2D,GLES20.GL_TEXTURE_MAG_FILTER,GLES20.GL_LINEAR);
            GLES20.glTexParameterf(GLES20.GL_TEXTURE_2D, GLES20.GL_TEXTURE_WRAP_S,GLES20.GL_CLAMP_TO_EDGE);
            GLES20.glTexParameterf(GLES20.GL_TEXTURE_2D, GLES20.GL_TEXTURE_WRAP_T,GLES20.GL_CLAMP_TO_EDGE);
            GLUtils.texImage2D(GLES20.GL_TEXTURE_2D, 0, GLES20.GL_RGBA,mbitmap, 0);
        }
        assert mbitmap != null;
        mbitmap.recycle();
        Pic.close();
        Log.i(TAG, "Texture loading succeed" + Arrays.toString(texture));
        return texture[0];
    }catch (Exception e){
        Log.i(TAG, e.toString());
        return texture[0];
    }
}
```