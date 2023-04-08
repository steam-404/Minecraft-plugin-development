spigot中文文档

[概览 (Spigot-API 1.19.2-R0.1-SNAPSHOT API 中文文档) (windit.net)](https://bukkit.windit.net/javadoc/)



```java
// 写一个小案例
//玩家加入服务器时向当前在线玩家欢迎
//新建playerJoin.java

import org.bukkit.event.Listener;
import org.bukkit.event.EventHandler;
import org.bukkit.event.player.PlayerJoinEvent;

public class playerJoin implements Listener {
    //监听接口
    
    @EventHandler
    public void on_playerJoinService(PlayerJoinEvent playerJoinEvent) {
        //PlayerJoinEvent玩家加入
        
        String player = playerJoinEvent.getPlayer().getName();
        //获取玩家昵称
        
        playerJoinEvent.setJoinMessage(player+"加入了服务器");
        //设置加入时的信息
    }
}

```




```java
//注册的两种方式
this.getServer().getPluginManager().registerEvents(new playerJoin(),this);
Bukkit.getPluginManager().registerEvents(new playerJoin(), this);
```





![alt png](\screenshot\playerJoinService.png)
