# Chunkeys-Auction-Mod

Chunkeys Auction - Fabric 1.21.11 (client-side)

BUILD (Windows): double-click build.bat  -> build\libs\chunkeys-auction-2.0.0.jar
Needs JDK 21. Put the jar in .minecraft\mods with Fabric API.

GUI: press INSERT (change it in Options > Controls > Key Binds > Chunkeys Auction) or type /auction.
Type an item name like "netherite ingot" or click Select to search every item/block.

COMMANDS
/auction start <item> <time> <minimum>   e.g. /auction start minecraft:diamond_sword 5m 100
/auction hand <time> <minimum>           uses the item in your hand
/auction status | stop | cancel | extend <time>
/auction test <player> <amount>          fake a payment to try it
/auction announce on|off                 also post updates in public chat (default off)
/auction cumulative on|off               add up each player's payments (default off)
/auction debug on|off                    (shows what the server sends when someone pays)
/auction hud on|off                      (move it: HUD Position button in the menu)
/auction regex [pattern|reset]           how payments are detected from chat

Time: 90, 30s, 5m, 1h30m.  Amounts: 100, 1,000, 5k, 1.5m.
Payments are read from chat lines like "Bob paid you $100".
A payment below the minimum (or not higher than the top bid) only updates "Last paid".

SETTINGS: open the menu (INSERT) and click Settings (top-left). Debug, action bar reading, auction-house sale detection and both patterns are there.
Auction-house sales ("X bought ... for $Y") count as bids when enabled. If DonutSMP words it differently, turn Debug on, copy the line, and edit the sale pattern.

OWN PURCHASES: lines where YOU buy/pay for something (auction house, shop, "You bought ... for $X", "Purchased ...", "from the shop") are ignored, never counted as bids or last paid. Toggle: Settings > "Ignore my own shop/AH purchases" (default ON). Debug shows them as "ignored (my own purchase)".

AMOUNT: set how many you're selling in the Amount box (any number, e.g. 5, 10, 64, 500). Press "Held" and it fills the Amount with the stack in your hand (e.g. holding 10 netherite = 10), and you can still type over it. It shows on the HUD, chat and announcements as "10x Netherite Ingot".
Commands: /auction start <item> <time> <minimum> [amount]    /auction hand <time> <minimum> [amount]  (hand defaults to the stack you hold)

WORTH: servers that print a value in the item tooltip (e.g. "~$ 12K") - press Held (or Select) and the mod reads that number into the Worth box. You can also type it. It shows on the HUD, in chat and in the announcement. "Set as minimum" copies it into the Minimum box. /auction hand reads it automatically too.
