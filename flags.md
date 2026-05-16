# Coat of Arms modding
*Coat of Arms* or *CoA* or *Flags*
In the future, all Coat of Arms will be called Flags.

The flag files are located in two directories, the graphic files are located in `gfx/coat_of_arms/`, and the configuration is already in `common/coat_of_arms/`.
**This guide will cover only the graphical part and the basic configuration of the flags.**

## Basics
Flags consist of 3 elements, these are **color**, **pattern** and **emblem**. Emblems are divided into **textured** and **colored**.

### Color
The colors are specified either in the flag configuration file or in a separate color file in the `common/named_colors/` directory. The game supports **rgb** and **hsv** formats.
In the flag configuration, you can specify the flag color in two ways **tag** or **color code**.
`color1 = custom_flag_color`,
`color1 = rgb { 255 255 255}`/
`color1 = hsv { 1.0 1.0 1.0}`
If you use **tag** for the flag color, you need to specify its color in the file in `common/named_colors/`.
```
colors = {
	custom_flag_color = rgb { 255 255 255}
}
```
### Pattern
It is used as the base of the flag. Uses images from `gfx/coat_of_arms/patterns/`, up to 3 colors can be used in the image. In the future, each of these colors can be used as a **mask** for **emblem**.
| color | name | rgb code |
| --- | --- | --- |
| 1 | color1 | 255 0 0 |
| 2 | color2 | 255 255 0 |
| 3 | color3 | 255 255 255 |
<img src="https://github.com/MIUNO/ImperatorRomeNotes/blob/main/images/example-3.png?raw=true" alt="" width="128" height="85">

#### Example
```
FRA = {
	pattern = "pattern_tricolor_vertical_01.tga"
	color1 = "FRA_blue"
	color2 = "full_white"
	color3 = "FRA_red"
}
```
<img src="https://github.com/MIUNO/ImperatorRomeNotes/blob/main/images/3color.png?raw=true" alt="" width="470" height="102">

### Emblem
Emblems allows you to add additional images to the flag, they are divided into **textured** and **colored**. You can also control their display on the flag using **position**, **scale**, **rotation** and **mask**.
**Position** is used to position the **emblem** on the flag.
**Scale** is used to change the size of the **emblem** on the flag.
```
	textured_emblem = {
		texture = "n_america/RUA/RUA_eagle.dds"
		instance = { position = { 0.5 0.5 } scale = { 0.5 0.5 } }
	}
```
<img src="https://github.com/MIUNO/ImperatorRomeNotes/blob/main/images/textured_emblem.png?raw=true" alt="" width="470" height="102">

**Rotation** used to rotate the emblem on the flag.
```
	colored_emblem = {
		texture = "europe/POR/POR_coa.dds"
		color1 = "POR_yellow"
		color2 = "full_black"
		color3 = "full_black"
		instance = { position = { 0.5 0.62 } scale = { 0.37 0.6 } rotation = 45 }
	}
```
<img src="https://github.com/MIUNO/ImperatorRomeNotes/blob/main/images/rotation.png?raw=true" alt="" width="470" height="102">

**Mask** used to color a specific flag color.
```
	pattern = "pattern_diagonal_split_01.tga"
	color1 = "full_white"
	color2 = "POR_blue"

	colored_emblem = {
		texture = "europe/POR/POR_coa.dds"
		color1 = "POR_yellow"
		color2 = "full_black"
		color3 = "full_black"
		instance = { position = { 0.5 0.62 } scale = { 0.37 0.6 } }
		mask = { 1 }
	}
```
<img src="https://github.com/MIUNO/ImperatorRomeNotes/blob/main/images/mask.png?raw=true" alt="" width="470" height="102">

### Textured emblem
They use images from the directory `gfx/coat_of_arms/textured_emblems/`.

#### Example
```
	textured_emblem = {
		texture = "n_america/RUA/RUA_eagle.dds"
		instance = { position = { 0.5 0.5 } scale = { 0.5 0.5 } }
	}
```
<img src="https://github.com/MIUNO/ImperatorRomeNotes/blob/main/images/textured_emblem.png?raw=true" alt="" width="470" height="102">

### Colored emblem
They use images from the directory `gfx/coat_of_arms/colored_emblems/`.
The vanilla version of **ImperatorRome** uses **emblem** with only 2 colors when using the file `[gfx/FX/coat_of_arms/coat_of_arms_textured_emblem.shader](https://github.com/MIUNO/ImperatorRomeNotes/blob/main/gfx/FX/coat_of_arms/coat_of_arms_textured_emblem.shader)` they can be expanded to 3x, but vanilla emblems will no longer work, while you can use emblems from new *Paradox* games such as **ck3**, **vic3** or **eu5**.

#### Colored emblem colors
| color | name | R | G | B (brightness) |
| --- | --- | --- | --- | --- |
| vanilla | color1 | 255 | 0 | 128 |
| vanilla | color2 | 255 | 255 | 128 |
| vanilla | color3 | | | |
| custom | color1 | 0 | 0 | 128 |
| custom | color2 | 0 | 255 | 128 |
| custom | color3 | 255 | 0 | 128 |

By default, the brightness is 128, when using values in the range from 0 to 255, the set color will be darker or brighter, respectively.

Visual range of colors (not exact): **Vanilla**/**Custom**

<img src="https://github.com/MIUNO/ImperatorRomeNotes/blob/main/images/example-1.png?raw=true" alt="" width="128" height="85"> <img src="https://github.com/MIUNO/ImperatorRomeNotes/blob/main/images/example-2.png?raw=true" alt="" width="128" height="85">

Example emblems: **Vanilla**/**Custom**

<img src="https://github.com/MIUNO/ImperatorRomeNotes/blob/main/images/example-4.png?raw=true" alt="" width="128" height="128"> <img src="https://github.com/MIUNO/ImperatorRomeNotes/blob/main/images/example-5.png?raw=true" alt="" width="128" height="128">

#### Example
```
	colored_emblem = {
		texture = "europe/POR/POR_coa.dds"
		color1 = "POR_yellow"
		color2 = "full_black"
		color3 = "full_black"
		instance = { position = { 0.5 0.62 } scale = { 0.37 0.6 } }
	}
```
<img src="https://github.com/MIUNO/ImperatorRomeNotes/blob/main/images/colored_emblem.png?raw=true" alt="" width="470" height="102">

### Sub
It is used to add ready-made flags to the flag.

#### Example
```
    sub = {
		parent = "SPA" 
		instance = { scale = { 0.5 0.5 } }
    }
```
<img src="https://github.com/MIUNO/ImperatorRomeNotes/blob/main/images/sub.png?raw=true" alt="" width="470" height="102">

## Additionally
Additionally, you can read the articles on the wiki: [ir](https://imperator.paradoxwikis.com/Coat_of_arms_modding) [ck3](https://ck3.paradoxwikis.com/Coat_of_arms_modding) [vic3](https://vic3.paradoxwikis.com/Flag_modding) [eu5](https://eu5.paradoxwikis.com/Flag_modding)

### Mipmap
Although this is not so noticeable, using **mipmap** allows you to keep the detail of the flags when they are reduced.

#### No use mipmap/use mipmap
<img src="https://github.com/MIUNO/ImperatorRomeNotes/blob/main/images/no_use_mipmap.png?raw=true" alt="" width="470" height="102">
<img src="https://github.com/MIUNO/ImperatorRomeNotes/blob/main/images/use_mipmap.png?raw=true" alt="" width="470" height="102">

### Pink artifacts
When using the Colored emblem, there may be a problem with pink artifacts along the outline of the emblem.

#### Example artifacts
```
	colored_emblem = {
		texture = "europe/POR/POR_coa.dds"
		color1 = "POR_yellow"
		instance = { position = { 0.5 0.62 } scale = { 0.37 0.6 } }
	}
```
<img src="https://github.com/MIUNO/ImperatorRomeNotes/blob/main/images/color_bug.png?raw=true" alt="" width="470" height="102">

This can be fixed by adding black to the remaining colors, for example.

#### Example fix
```
	colored_emblem = {
		texture = "europe/POR/POR_coa.dds"
		color1 = "POR_yellow"
		color2 = "full_black"
		color3 = "full_black"
		instance = { position = { 0.5 0.62 } scale = { 0.37 0.6 } }
	}
```
<img src="https://github.com/MIUNO/ImperatorRomeNotes/blob/main/images/color_fix.png?raw=true" alt="" width="470" height="102">

### White artifacts
The brother of the pink artifact, but white

#### Example fix
Due to errors during export, completely transparent white pixels may appear, they are to blame for everything. To fix this, you need to select all these pixels and delete them, as a result they will turn black with the same completely transparency.
<img src="https://github.com/MIUNO/ImperatorRomeNotes/blob/main/images/example-6-paintnet.png?raw=true" alt="" width="709" height="187">

<img src="https://github.com/MIUNO/ImperatorRomeNotes/blob/main/images/example-7-paintnet.png?raw=true" alt="" width="465" height="297">

### Alpha Channel Filtering
A simple shader add-on for alpha channel filtering removes the *glow effect* around the **color_emblem**.
`[gfx/FX/coat_of_arms/coat_of_arms_textured_emblem.fxh](https://github.com/MIUNO/ImperatorRomeNotes/blob/main/gfx/FX/coat_of_arms/coat_of_arms_textured_emblem.fxh)`

## Ready flag example
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
#### Result
<img src="https://github.com/MIUNO/ImperatorRomeNotes/blob/main/images/ready_flag.png?raw=true" alt="" width="470" height="102">
