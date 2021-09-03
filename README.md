# Creatorul de badgeuri :mage_man:
Script Python facut pentru completarea automata a badgeurilor de Teambuilding.

<hr>
<div align="center">
<img src="https://cdn.icon-icons.com/icons2/112/PNG/512/python_18894.png" width="45" height="45"/>
<img src="https://upload.wikimedia.org/wikipedia/commons/thumb/2/20/Photoshop_CC_icon.png/615px-Photoshop_CC_icon.png" width="35" height="35"/>
</div>
<hr>

### Demo

<img src="https://user-images.githubusercontent.com/61749814/132041715-9009c6ad-cc3f-4005-805f-f220c0b1530d.gif" width="550" height="300"/>

### Cum se foloseste?
#### :point_right: Daca nu vrei alte schimbari in cod
Downloadeaza tot ce se afla in folderul ```Project``` si executa ```main.py```.

#### :point_right: Daca ai nevoie de schimbari in cod
Introduce in GitBash comanda: ```git clone https://github.com/as-mi/Creatorul-de-badgeuri.git```.

### Specificatii (daca nu vrei sa modifici codul):
:diamond_shape_with_a_dot_inside: Dimensiune: ```750 x 1181 px```.

:diamond_shape_with_a_dot_inside: Format: ```.jpg```.

:diamond_shape_with_a_dot_inside: Tabelul Excel contine numele voluntarilor grupati pe departamente: CD, Alumn, Design&PR, HR, FR, Edu, Proiecte.

:diamond_shape_with_a_dot_inside: Numele badgeurilor corespund cu numele coloanelor din documentul Excel.

:diamond_shape_with_a_dot_inside: Versiuni Photoshop ```2020```, ```cc2019```, ```cc2018```, ```cc2017```.

:diamond_shape_with_a_dot_inside: Daca numele de familie este mai lung ca 11 caractere, va reduce automat dimensiunea fontului.
```python
# Font size depends on family name length
      if len(family_name) > 10:
            FONT_SIZE = FONT_SIZE - len(family_name) 
            font_size_px = ImageFont.truetype(FONT_PATH , FONT_SIZE)
      else:
            font_size_px = ImageFont.truetype(FONT_PATH , FONT_SIZE)
 ```

### Ce poti face cu aceasta aplicatie?
:heavy_check_mark: Introduci un folder local de pe PC unde ai designul badgeurilor.

:heavy_check_mark: Introduci tabelul Excel cu numele departamentelor si voluntarilor.

:heavy_check_mark: Introduci fontul pe care vrei sa-l folosesti(```.ttf``` file).

:heavy_check_mark: Introduci culoarea textului (valoarea RGB).

:heavy_check_mark: Introduci dimensiunea textului (masurata in unitati - aceeasi ca in Photoshop).

### Ai nevoie sa modifici codul daca vrei:
:hammer_and_wrench: Sa schimbi pozitia numelor si dimensiunile badgeurilor.
```python
# Script_PS.py
[...]

POSITION_Y = 750
DOC_WIDTH = 827 #pixels

[...]

# X units * 0.75 (px/unit)
new_text_layer.textItem.position = [DOC_WIDTH / 2 - maximum_length[0] / (FONT_SIZE * 0.75), POSITION_Y] # [OX, OY]
``` 
*Formula care pozitioneaza numele relativ la linia verticala ```DOC_WIDTH / 2 - maximum_length[0] / (FONT_SIZE * 0.75)```*

:hammer_and_wrench: Schimbarea numelor departamentelor implica schimbarea numelor badgeurilor model.

*Asta nu are nevoie de schimbari in cod. Schimbarile se vor face doar in documentul Excel si la numele badgeurilor model.*

:hammer_and_wrench: Dezactivarea stilurilor: bold si strong.  
```python
#Script_PS.py
[...]

new_text_layer.textItem.antiAliasMethod = AntiAlias(4) # 4 coresponds to Strong property
[...]

new_text_layer.textItem.fauxBold = True
```

### Tehnologii folosite :woman_technologist:

 ```Python v3.8.5```

- ```photoshop_python_api``` Interactiunea cu aplicatia Photoshop. [Documentatia aici](https://photoshop-python-api.readthedocs.io/en/master/).
- ```Tkinter``` Librarie GUI. [Documentatia aici](https://docs.python.org/3/library/tk.html).

