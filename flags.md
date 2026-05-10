# Coat of Arms modding
*Coat of Arms* or *CoA* or *Flags*
В дальнейшем все Coat of Arms будут называться Флагами.

Файлы флагов распологаются в двух директориях, графические файлы находятся в `gfx/coat_of_arms/`, а конфигурация уже в `common/coat_of_arms/`.
**В данном руководстве будет рассмотрена только графическая часть и базовая конфигурация флагов.**

# Основы
Флаги состоят из 3х элементов, это **color**, **pattern** and **emblem**. Эмблемы же разделяются на **textured** and **colored**.

### Color
Цвета указываются либо в файле конфигурации флага, либо в отдельном файле с цветами в директории `common/named_colors/`. Игра поддерживает форматы **rgb** and **hsv**.
В конфигурации флага можно указать цвет флага двумя способами **tag** or **color code**.
`color1 = custom_flag_color`,
`color1 = rgb { 255 255 255}`/
`color1 = hsv { 1.0 1.0 1.0}`
В случае использования **tag** для цвета флага, нужно указать его цвет в файле в `common/named_colors/`.
```
colors = {
	custom_flag_color = rgb { 255 255 255}
}
```
### Pattern
Используется как основа флага. Использует изображения из `gfx/coat_of_arms/patterns/`, в изображение может использоваться до 3х цветов. В последующем каждый из этих цветов можно будет использовать как **mask** for **emblem**.
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
Emblems позволяют добавлять дополнительные изображения на флаг, они разделяются на **textured** and **colored**. А так-же можно управлять их отображением на флаге при помощи **position**, **scale**, **rotation** and **mask**.
**Position** используется для расположения **emblem** на флаге.
**Scale** используется для изменения размера **emblem** на флаге.
```
	textured_emblem = {
		texture = "n_america/RUA/RUA_eagle.dds"
		instance = { position = { 0.5 0.5 } scale = { 0.5 0.5 } }
	}
```
<img src="https://github.com/MIUNO/ImperatorRomeNotes/blob/main/images/textured_emblem.png?raw=true" alt="" width="470" height="102">

**Rotation** используется для поворота emblem на флаге.
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

**Mask** используется для расположения 
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
Используются изображения из директории `gfx/coat_of_arms/textured_emblems/`.
#### Example
```
	textured_emblem = {
		texture = "n_america/RUA/RUA_eagle.dds"
		instance = { position = { 0.5 0.5 } scale = { 0.5 0.5 } }
	}
```
<img src="https://github.com/MIUNO/ImperatorRomeNotes/blob/main/images/textured_emblem.png?raw=true" alt="" width="470" height="102">

### Sub
Используется для добавления на флаг уже готовых флагов.
#### Example
```
    sub = {
		parent = "SPA" 
		instance = { scale = { 0.5 0.5 } }
    }
```
<img src="https://github.com/MIUNO/ImperatorRomeNotes/blob/main/images/sub.png?raw=true" alt="" width="470" height="102">
