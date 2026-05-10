
# Coat of arms modding
*Coat of arms* or *CoA* or *Flags*

Файлы флагов распологаются в двух директориях, графические файлы находятся в `gfx/coat_of_arms/`, а логическая уже в `common/coat_of_arms/`.


### Ready flag example
```
POR = {
	pattern = "pattern_solid.tga"
	color1 = "full_white"
	color2 = "POR_blue"

	colored_emblem = {
		texture = "europe/POR/POR_coa.dds"
		color1 = "POR_yellow"
		color2 = "full_black"
		color3 = "full_black"
		instance = { position = { 0.5 0.62 } scale = { 0.37 0.6 } }
	}
	colored_emblem = {
		texture = "symbols/shield_01.dds"
		color1 = "POR_yellow"
		color2 = "full_black"
		color3 = "full_black"
		instance = { position = { 0.5 0.6 } scale = { 0.22 0.5 } }
	}
	colored_emblem = {
		texture = "symbols/shield_01.dds"
		color1 = "POR_red"
		color2 = "full_black"
		color3 = "full_black"
		instance = { position = { 0.5 0.6 } scale = { 0.2 0.46 } }
	}
	colored_emblem = {
		texture = "symbols/shield_01.dds"
		color1 = "full_white"
		color2 = "full_black"
		color3 = "full_black"
		instance = { position = { 0.5 0.595 } scale = { 0.1 0.26 } }
	}
	colored_emblem = {
		texture = "europe/POR/POR_shield.dds"
		color1 = "POR_blue"
		color2 = "POR_blue"
		color3 = "POR_blue"
		instance = { position = { 0.47 0.59 } scale = { 0.035 0.05 } }
		instance = { position = { 0.5 0.53 } scale = { 0.035 0.05 } }
		instance = { position = { 0.5 0.59 } scale = { 0.035 0.05 } }
		instance = { position = { 0.5 0.65 } scale = { 0.035 0.05 } }
		instance = { position = { 0.53 0.59 } scale = { 0.035 0.05 } }
	}
	colored_emblem = {
		texture = "europe/POR/POR_castle.dds"
		color1 = "POR_yellow"
		color2 = "full_black"
		color3 = "full_black"
		instance = { position = { 0.43 0.58 } scale = { 0.04 0.05 } }
		instance = { position = { 0.43 0.46 } scale = { 0.04 0.05 } }
		instance = { position = { 0.43 0.7 } scale = { 0.04 0.05 } }
		instance = { position = { 0.57 0.58 } scale = { 0.04 0.05 } }
		instance = { position = { 0.57 0.46 } scale = { 0.04 0.05 } }
		instance = { position = { 0.57 0.7 } scale = { 0.04 0.05 } }
		instance = { position = { 0.5 0.46 } scale = { 0.04 0.05 } }
	}
	colored_emblem = {
		texture = "europe/POR/POR_crown.dds"
		color1 = "POR_yellow"
		color2 = "POR_red"
		color3 = "SPA_green"
		instance = { position = { 0.5 0.22 } scale = { 0.26 0.4 } }
	}
}
```
### Result
<img src="https://github.com/MIUNO/ImperatorRomeNotes/blob/main/images/ready_flag.png?raw=true" alt="" width="470" height="102">

