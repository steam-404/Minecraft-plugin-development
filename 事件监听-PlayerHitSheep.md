```java
//玩家攻击羊时，服务器广播
import org.bukkit.Bukkit;
import org.bukkit.entity.Entity;
import org.bukkit.entity.Player;
import org.bukkit.entity.Sheep;
import org.bukkit.event.EventHandler;
import org.bukkit.event.Listener;
import org.bukkit.event.entity.EntityDamageByEntityEvent;

public class playerHitSheep implements Listener {
    @EventHandler
    public void on_playerHitSheep(EntityDamageByEntityEvent event) {
        Entity damager=event.getDamager();
        String player=damager.getName();
        //获取玩家昵称
        
        if(damager instanceof Player){
            //判定攻击者是玩家
            if(event.getEntity() instanceof Sheep){
                //受害者是羊
                Bukkit.broadcastMessage("玩家:"+player+"正在攻击羊");
            }
        }
    }
}
```



```java
Bukkit.getPluginManager().registerEvents(new playerHitSheep(),this);
//注册插件
```



![alt png](screenshot\playerHitSheep.png)

