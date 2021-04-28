# Just Enough Items (JEI)

This mod displays the in-game recipes. It is highly recommended to use if you develop a modpack, because it can display the modified recipes according your configuration.

![](/images/mod_jei_hero.png)

## Details

- Version: 1.8+ to 1.16+ | Forge
- Mod author: [mezz](https://www.curseforge.com/members/mezz)
- Download at [CurseForge](https://www.curseforge.com/minecraft/mc-mods/jei)
- [GitHub issues](https://github.com/mezz/JustEnoughItems/issues)

## Start with mod

Install the mod jar file and you are good to go.

## Basic Controls

### Bookmarks

Hover over the item you want to add to the bookmarks (left side of the screen) and press ++a++ on your keyboard. To remove item from the bookmarks, do the same.

### Inventory

Show Recipes
:	Hover over item + ++"R"++

Show Uses
:	Hover over item + ++"U"++

### Item List

Show Recipes
:	++"Click"++ Item or press ++"R"++

Show Uses
:	++"Right-click"++ Item or press ++"U"++

Next/Previous page
:	Scroll Wheel on the mouse or click the arrow buttons on the top right corner of your screen

Open Config Menu
:	++"Click"++ Wrench at bottom-right corner

Toggle Cheat mode
:	++ctrl+"click"++ Wrench at bottom-right corner (Windows/Linux)
:	++cmd+"click"++ Wrench at bottom-right corner (macOS)

### Search bar

Select Search Bar
:	++"Click"++ or ++ctrl+"F"++ (Windows/Linux)
:	++"Click"++ or ++cmd+"F"++ (macOS)

Clear Search
:	++"Right-click"++ with the mouse

Previous Search
:	++up++ arrow on the keyboard

Search by Mod Name
:	Type @ in front of a word, for example: @thaum
:	Multiple terms work together, for example: wand @thaum

Exclude search terms
:	Type - in front of a word, for example: @thaum -wand

Search terms that have spaces in them
:	Type "" around the words, for example: "two words"

### Recipe View

Next/Previous page
:	Scroll Wheel

Previous recipe
: ++back++

Show all Recipes
:	Click the recipe category's name

Move items into crafting area
:	Click the ++"\+"++ button. ++shift+"click"++ to move multiple sets of items.


## Features

* Easier recipe view and you don't have to remember every recipe.
* Plus ++"\+"++ button to add the recipe instantly into your crafting table.
* ++shift+"click"++ on the ++"\+"++ button to add all the available items from the recipes into your crafting table.

## Commands

There are no commands added by the mod.

## Config

### Disabling items in 1.10.2 to 1.12.2

#### Using JEI

File location: `config/JEI/itemBlacklist.cfg`

Let's disable for example all Applied Energistics 2 facades (line 16) and the items added by Recurrent Complex mod entirely (line 17).

```cfg
# Configuration file @ config/JEI/itemBlacklist.cfg

#############################################################
# advanced
#-----------------------------------------------------------#
# Advanced config options to change the way JEI functions.
#############################################################

advanced {
    # List of items that should not be displayed in the item list.
    # Format: modId[:name[:meta]].
    # Edit Mode will automatically add or remove entries here. 
    # [Default: []]

    S:itemBlacklist <
        appliedenergistics2:facade
        reccomplex
     >
}
```

#### Using CraftTweaker on 1.12

In this case we are **hiding** diamond, water, lava (line 2, 5, 6). These items can be crafted if you know the recipe. But we also **removing** the Iron Leggings (line 10) and every planks (line 11). This way you can not view and craft these items.

More info and source at the official [CraftTweaker Documentation](https://docs.blamejared.com/1.12/en/Mods/JEI/JEI/) site.

!!! info
	You need to install CraftTweaker to use the code below with JEI!

```java
//hide(IItemStack item);
mods.jei.JEI.hide(<minecraft:diamond>);

//hide(ILiquidStack item);
mods.jei.JEI.hide(<liquid:water>);
mods.jei.JEI.hide(<fluid:lava>);


//removeAndHide(IIngredient output, @optional boolean NBT-Match)
mods.jei.JEI.removeAndHide(<minecraft:iron_leggings>);
mods.jei.JEI.removeAndHide(<ore:planks>, false);
```