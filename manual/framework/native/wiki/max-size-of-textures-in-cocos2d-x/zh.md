

#各个平台支持的Cocos2d-x最大纹理尺寸


从理论上讲，Cocos2d-x可以显示任何尺寸的纹理，但实际上的纹理的MAXSIZE是由硬件和系统的限制。 
在这里，我提供在不同平台上的仿真器纹理大小限制表。

|平台|最大像素尺寸|
|------------|------------|
|win32	|2048 * 2048|
|android	|4096 * 4096|
|iPhone3	|1024 * 1024|
|iPhone3GS	|2048 * 2048|
|iPhone4	|2048 * 2048|


在真机上，他们也有不同的限制，这里有一些测试结果：G3（hero）1024*1024，iPhone4的2048*2048。 

因此，对于开发者，如果你想使你的游戏运行流畅且跨平台，你应该保持你的纹理尺寸小于1024*1024，对于大多数机器，这是最低的限制。 

代码获得的设备支持纹理最大尺寸：（可能无法在模拟器中使用）

```
GLint m_maxTextureSize = 0;
glGetIntegerv(GL_MAX_TEXTURE_SIZE, &m_maxTextureSize);
```
