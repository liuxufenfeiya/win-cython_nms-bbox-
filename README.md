# win-cython_nms-bbox-
几个常见的报错：

  1.AttributeError: ‘MSVCCompiler’ object has no attribute ‘compiler_so’

  2.ValueError: Buffer dtype mismatch, expected ‘int_t’ but got 'long long

  3.ImportError: cannot import name ‘bbox’

  4.mv: 无法获取’utils/*’ 的文件状态(stat): No such file or directory

原因分析：
  1.这个问题在win7上无解，无论怎么安装vs2015还是.net什么都没用，win10上是可以的，亲测有效；

  2.很多人说什么把int改成intp，毛用都没有

  3.这个是纯编译问题，win7上貌似没办法编译

  4.这个是编译好了会生成一个什么.so文件，但是这个文件没法复制，我也不是很懂怎么mv，这个问题linux不会发生，win7，win10都不行


针对这些问题，我的最终解决方案就是，用win10的机器编译好了常见的几个，
如bbox、cython_nms（在有的模型里import的代码名称可能不同，改个文件名就好）

win下的cpu版本，这6个文件，貌似有用的就那两个pyd文件，复制过去就好了，或者6个文件一起复制过去，
这样就不用运行此文件夹下的什么.sh文件对c++编译了，也就不用配置什么gcc之类的文件了
