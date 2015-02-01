package me.BTTFHamsterZK.Core;

import java.io.File;

import org.bukkit.Material;
import org.bukkit.block.Block;
import org.bukkit.command.Command;
import org.bukkit.command.CommandSender;
import org.bukkit.entity.Entity;
import org.bukkit.entity.Player;
import org.bukkit.entity.TNTPrimed;
import org.bukkit.event.EventHandler;
import org.bukkit.event.EventPriority;
import org.bukkit.event.Listener;
import org.bukkit.event.block.Action;
import org.bukkit.event.block.BlockPlaceEvent;
import org.bukkit.event.entity.EntityExplodeEvent;
import org.bukkit.event.player.PlayerInteractEvent;
import org.bukkit.plugin.java.JavaPlugin;

public class Core extends JavaPlugin implements Listener {
	
	@Override
	public void onEnable(){
		getServer().getPluginManager().registerEvents(this, this);
		if (!(new File(getDataFolder(), "config.yml")).exists()){
			saveDefaultConfig();
		if (!(new File(getDataFolder(), "readme.yml")).exists()){
        	saveDefaultConfig();
        }
		}
	}
	
	@EventHandler
	public void onBoom(EntityExplodeEvent event){
		Entity entity = event.getEntity();
		if (entity !=null){
			if ((entity instanceof TNTPrimed)){
				event.blockList().clear();
			}
		}
	}
	
	@EventHandler(priority=EventPriority.HIGHEST)
	public void onPlace(BlockPlaceEvent event){
		Player player = event.getPlayer();
		Block block = event.getBlock();
		if (player.isOp() && block.getType()==Material.TNT){
			player.sendMessage("§4You are not able to place block TNT");
			event.setCancelled(true);
		}
	}
	
	@Override
	public void onDisable(){
	}
	
	@EventHandler
	public void onInteract(PlayerInteractEvent event){
		Player player = event.getPlayer();
		if (event.getAction()==Action.RIGHT_CLICK_BLOCK){
			Block block = event.getClickedBlock();
			if (player.isSneaking()){
				block.setType(Material.CAULDRON);
				player.sendMessage("§aThis works!");
			}
		}
	}
	
	@Override
	public boolean onCommand(CommandSender sender, Command cmd, String label, String[] args) {
		
		if (cmd.getName().equalsIgnoreCase("plugins")){
			
			sender.sendMessage("§fPlugins (§a1§f): §aTesting Plugin");
			
			return true;
		}
		
		else if (cmd.getName().equalsIgnoreCase("info")){
			
			sender.sendMessage("§cInfo§7§l >§r§c Test V1.0");
			sender.sendMessage("§cInfo§7§l >§r§6 Dev: BTTFHamsterZK");
			sender.sendMessage("§cInfo§7§l >§r§e Test Server");
			sender.sendMessage("§cInfo§7§l >§r§a MC1.8/1.7");
			sender.sendMessage("§cInfo§7§l >§r§b null Players Online");
			sender.sendMessage("§cInfo§7§l >§r§d Playing as null");
			sender.sendMessage("§7§o Yes, the nulls were intentional :)");
			
			return true;
		}
		
		else if (cmd.getName().equalsIgnoreCase("whatdoido")){
			
			sender.sendMessage("§7§oThis plugin (Coded by BTTFHamsterZK) is made for a TEST, not for a real plugin.");
			sender.sendMessage("§c+ §rThis plugin adds commands (/info, /plugins, /help, /whatdoido)");
			sender.sendMessage("§c+ §rIt also blocks TNT from being placed.");
			sender.sendMessage("§c+ §rSneak, Right click block changes to cauldron :D");
			
			return true;
		}
		
		else if (cmd.getName().equalsIgnoreCase("owners")){
			
			sender.sendMessage("§cThis Servers Owners");
			sender.sendMessage("§aBTTFHamsterZK §7§oTechnical Manager");
			sender.sendMessage("§aHDCreeper §7§oCommunity Manager");
			sender.sendMessage("§aDerpySquid69 §7§oTester");
			
			return true;
		}
		
		else if (cmd.getName().equalsIgnoreCase("help")){	
				
				sender.sendMessage("Running OnAndOff V1.0 §7By BTTFHamsterZK");
			
				return true;
	        }
			return false;
	    }
}
