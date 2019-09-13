# Gradle note

## gradle包装器：gradle wrapper
gradle不需要我们自己下载安装，在项目根目录下有Gradle的安装配置文件和相关的shell脚本：
gradle-wrapper.properties:配置了Gradle下载版本和下载地址等
gradlew:Mac or Linux端的shell脚本
gradle.bat:Window的shell脚本

## Task
1.Gradle中最小的执行单元，task用于描述要执行的动作，允许输入和输出，task之间允许存在依赖关系，在task执行时，会先构建task之间的依赖关系，按照被依赖的优先级执行task
2.执行./gradlew tasks会按照group输出当前支持的任务和相关描述,Android中常见的任务分别在Build和help的组里面
3.默认gradle task都是在后台运行的，这样能提高执行效率
4.在build.gradle中定义的task会委托给该文件对应的project，peoject对象本身提供了一下api，比如
  project.task("myTask1") => 创建myTask1的任务，在当前文件中执行时可以省略project或者括号之类的，下列是等效的：
  project.task("myTask1") == task("myTask1") == task "myTask1"
  常见定义方式：
  task myTask1 << {
     println "hello word"
  }
5.task支持类型任务，比如Copy Delete Zip等，也可以自定义类型任务参照gradleTask.gradle的HelloNameTask
小技巧：
#### 执行某个gradle文件中的task
     ./gradlew -b filename.gradle taskName
     静默方式执行task
     ./gradlew -q taskName


