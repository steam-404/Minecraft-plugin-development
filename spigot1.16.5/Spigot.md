### MC插件开发

- 1.本地服务器搭建

​	下载核心[Spigot (getbukkit.org)](https://getbukkit.org/download/spigot), 以1.16.5为例

​	创建一个start.sh文件并写入以下内容,#表示设置的最大/最小内存,双击启动

```bash
@echo off
java -Xms#G -Xmx#G -XX:+UseG1GC -jar spigot-1.16.5.jar nogui 
pause
```

启动成功后使用`stop`命令关闭服务器,找到项目同级`eula.txt`文件,将eual的值改为`true`
重新启动start.sh文件

启动完成后使用mc进入服务器,服务器地址为:127.0.0.1或localhost(服务器和mc,版本必须一致)

服务器常用命令

| 命令 | 效果 |
| ---- | ---- |
| help | 帮助 |
|plugins|插件数量|
|stop|停止服务器|
|reload|重载服务器|






- 2.开发环境

  集成开发环境:`idea2021.3.1`  [Other Versions - IntelliJ IDEA (jetbrains.com)](https://www.jetbrains.com/idea/download/other.html)

  java版本:`jdk1.8` [Java | Oracle](https://www.java.com/zh-CN/)

  idea插件:`Mincraft Development`  [Minecraft Development - IntelliJ IDEA Plugin | Marketplace (jetbrains.com)](https://plugins.jetbrains.com/plugin/8327-minecraft-development)
  
  spigot创建完成后src主目录下有以下代码
  
  ```java
  package steam_404.learning;
  
  import org.bukkit.plugin.java.JavaPlugin;
  
  public final class Learning extends JavaPlugin {
  
      @Override
      public void onEnable() {
          // 插件加载时启动
          System.out.println("插件加载成功");//sout语句不会加载到日志里
  
      }
  
      @Override
      public void onDisable() {
          // 插件卸载时启动
      }
  }
  
  ```
  
  
  
  加载文本信息到日志中
  
  ```java
  package steam_404.learning;
  
  import org.bukkit.plugin.java.JavaPlugin;
  import org.bukkit.ChatColor;
  import java.util.logging.Logger;//导入日志模块
  
  public final class Learning extends JavaPlugin {
  
      @Override
      public void onEnable() {
          Logger logger = this.getLogger();//实例化logger对象
          logger.info("插件加载成功");//输出info级别信息
          Bukkit.getConsoleSender().sendMessage(ChatColor.BLUE + "插件加载成功");//自定义日志字体颜色
  
      }
  
      @Override
      public void onDisable() {
          
      }
  }
  
  ```
  
  
