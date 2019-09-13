## 构建参数化
构建参数来源：
  1.命令行 => -P key=value
  2.文件 => gradle.properties key=value 或者 ext{}块中定义 这两者是等效的
  3.环境变量
优先级：
命令行>file