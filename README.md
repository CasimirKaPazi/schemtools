Schemtools
==========

This mod contains some commands to create and handle schematics. You can select a world area, save it as a lua table and turn that table into a binary mts format. The lua format is handy because you can edit it by hand. Normal workflow would be to build your object in minetest, save it as lua, edit the lua file and then convert to mts.

Schemtools is mostly just the two mods *schematic_save* and *saveschems* combined.


```
local n1 = { name = "default:sand" }
local n2 = { name = "default:river_water_source" }
local n3 = { name = "default:river_water_flowing", param2 = 7 }
...

return {
	yslice_prob = {

	},
	size = {
		y = 14,
		x = 15,
		z = 11
	}
	,
	data = {
		n1, n1, n1, n1, n1, n1, n2, n2, n2, n2, n2, n2, n2, n2, n2, n3, n3, 
		n4, n4, n4, n4, n4, n5, n5, n5, n5, n5, n5, n5, n5, n5, n5, n5, n5, 
		n5, n5, n5, n5, n5, n5, n5, n5, n5, n5, n5, n5, n5, n5, n5, n5, n5, 
		...
	}
}
```

To use the file directly use dofile(path), which will give you the table.

Usage
-----

Some commands begin with "st" (**s**chem**t**ools) to distinguish them form the original worldedit ones.

### Set position
Go to a spot and type "/stp1", then another and type "/stp2". The volume in between is your schematic. By default air won't be placed.

### Save to lua
Then type in "/stsave <file>". The schematic will be saved in your world directory, with a ".lua" suffix. You can then copy it to an appropriate file and add register_decoration code.

### Convert to mts
To use a binary format type "/lua2mts <file>", where file is the one you previously created. The resulting mts file will also be saved in the world folder.

Almost all code is taken from:
------------------------------

[World Edit](https://github.com/Uberi/MineTest-WorldEdit)

[Schematic Saver](https://github.com/duane-r/schematic_save)

[Saveschems](https://github.com/paramat/saveschems) (for lua2mts)
