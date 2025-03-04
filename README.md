# Guide till Godot för 2D och 3D-spelutveckling

## Introduktion
Godot är en kraftfull och öppen källkod spelmotor som stöder både 2D och 3D-spelutveckling. Den erbjuder en flexibel nodbaserad arkitektur, inbyggt GDScript-programmeringsspråk och ett lättanvänt gränssnitt.

## Installation
1. Ladda ner Godot från [Godots officiella webbplats](https://godotengine.org/).
2. Installera och öppna programmet.
3. Skapa ett nytt projekt och välj en katalog för ditt spel.

## Grundläggande koncept
### Noder och Scener
- **Allt i Godot bygger på noder.**
- En scen kan innehålla flera noder.
- Exempel på vanliga noder:
  - `Node2D` - Grundläggande nod för 2D-spel
  - `Node3D` - Grundläggande nod för 3D-spel
  - `Sprite2D` - Hanterar bilder och texturer i 2D
  - `Camera3D` - Hanterar kameran i 3D

### GDScript
- Ett lättviktigt, Python-liknande skriptspråk som används för att programmera logik.
- Exempel på ett enkelt skript:

```gdscript
extends Node2D

func _ready():
    print("Spelet startar!")
```

## 2D-Spelutveckling
### Skapa en spelkaraktär
1. Lägg till en `Node2D` som root-nod.
2. Lägg till en `Sprite2D` och ladda en textur.
3. Lägg till en `CollisionShape2D` för kollisioner.
4. Lägg till en `KinematicBody2D` för rörelse.

### Enkel rörelse
```gdscript
extends KinematicBody2D

var speed = 200
var velocity = Vector2.ZERO

func _process(delta):
    velocity = Vector2.ZERO
    if Input.is_action_pressed("ui_right"):
        velocity.x += speed
    if Input.is_action_pressed("ui_left"):
        velocity.x -= speed
    move_and_slide(velocity)
```

## 3D-Spelutveckling
### Skapa en spelkaraktär i 3D
1. Lägg till en `Node3D` som root-nod.
2. Lägg till en `MeshInstance3D` och välj en 3D-modell.
3. Lägg till en `CollisionShape3D` för kollisioner.
4. Lägg till en `KinematicBody3D` för rörelse.

### Enkel rörelse i 3D
```gdscript
extends KinematicBody3D

var speed = 5
var velocity = Vector3.ZERO

func _process(delta):
    velocity = Vector3.ZERO
    if Input.is_action_pressed("ui_right"):
        velocity.x += speed
    if Input.is_action_pressed("ui_left"):
        velocity.x -= speed
    move_and_slide(velocity)
```

## Viktiga aspekter
- **Signals och Events:** Använd `signals` för att hantera händelser.
- **Scenhantering:** Återanvänd scener för bättre struktur.
- **Fysikmotor:** Godot har inbyggd fysik för både 2D och 3D.
- **Export:** Exportera spel till Windows, Linux, macOS, Android och HTML5.

## Slutsats
Godot är en kraftfull och flexibel spelmotor som erbjuder verktyg för både 2D och 3D-utveckling. Genom att förstå nodbaserad arkitektur, GDScript och fysikmotorn kan du snabbt skapa spel av hög kvalitet.

## Tutorial: Första 2D Spel
Gå igenom tutorialen ditt första 2D spel: [https://docs.godotengine.org/en/stable/getting_started/first_2d_game/index.html](https://docs.godotengine.org/en/stable/getting_started/first_2d_game/index.html)

För att först få en bekantskap med Godot. Därefter kan ni hoppa på 3D Spel.

Föredrar man video-tutorials är den här serien fantastisk för 2D spel med Godot:

[https://www.youtube.com/playlist?list=PL4cUxeGkcC9iHCXBpxbdsOByZ55Ez4bgF](https://www.youtube.com/playlist?list=PL4cUxeGkcC9iHCXBpxbdsOByZ55Ez4bgF)

## Tutorial: Första 3D Spel
Gå igenom tutorialen ditt första 3D spel: [https://docs.godotengine.org/en/stable/getting_started/first_3d_game/index.html](https://docs.godotengine.org/en/stable/getting_started/first_3d_game/index.html)

Föredrar man video-tutorials är den här serien fantastisk för 3D spel med Godot:

(https://www.youtube.com/playlist?list=PLda3VoSoc_TTp8Ng3C57spnNkOw3Hm_35)[https://www.youtube.com/playlist?list=PLda3VoSoc_TTp8Ng3C57spnNkOw3Hm_35]

## Projekt Beskrivning
Projektet utförs individuellt och går ut på att ni ska utveckla ett valfritt 2D-spel (240S) eller 3D-spel (230S) i Godot.

## Kravuppfyllelse på 2D spelet
### 1. Grundläggande spelmekanik
Spelarens rörelse – Piltangenter, WASD eller touch-input för rörelse.
Kollisionsdetektion – Säkerställa att objekt interagerar korrekt (t.ex. spelaren krockar med väggar).
Grundläggande mål – Ett enkelt mål som att nå en mållinje, samla föremål eller undvika hinder.
Vinst-/förlustvillkor – Ett sätt att avgöra om spelaren vinner eller förlorar.
### 2. Enkel grafik
Sprites – Enkla 2D-bilder för spelaren, fiender och bakgrund.
Tileset (valfritt) – Om spelet använder en tile-baserad miljö.
Minimala animationer – Åtminstone en enkel stillastående/rörelseanimation.
### 3. Grundläggande användargränssnitt (UI)
Startskärm – En enkel titelskärm med en "Starta"-knapp.
Game over-skärm – Ett meddelande när spelaren vinner eller förlorar.
HUD (valfritt) – Poängräknare, timer eller hälsovisning.
### 4. Enkla ljudeffekter och musik
Ljud för hopp, insamling eller kollisioner.
Bakgrundsmusik (slinga eller enkel låt).
### 5. Enkel AI eller spelelement (valfritt)
Grundläggande fienderörelse – Fiender rör sig vänster/höger eller jagar spelaren.
Samlarföremål – Mynt, stjärnor eller andra objekt.
Enkel fysik – Hopp/gravitationssystem om nödvändigt.
### 6. Scen- och nivåhantering
Enkla scenövergångar – Växla mellan nivåer eller starta om spelet.
Respawn eller återställning av spelet vid behov.

## Kravuppfyllelse på 3D spelet
### 1. Grundläggande spelmekanik
Spelarens rörelse – Använd WASD/tangenter eller en joystick för att styra en 3D-karaktär.
Kollisionsdetektion – Se till att spelaren och objekt inte går genom varandra.
Kamera – En enkel tredjepersons- eller förstapersonskamera som följer spelaren.
Grundläggande mål – Exempelvis att nå en specifik plats, samla föremål eller undvika hinder.
Vinst-/förlustvillkor – Enkla regler för att avgöra om spelaren vinner eller förlorar.
### 2. Enkel 3D-grafik
3D-modeller – Grundläggande objekt för spelaren, miljön och fiender (kan vara enkla former som kuber/sfärer).
Grundläggande texturer – Färger eller enkla bilder på modeller för att skapa variation.
Minimala animationer – Enkel gång- eller hopprörelse om spelet har en karaktär.
### 3. Grundläggande användargränssnitt (UI)
Startskärm – En enkel meny med en "Starta"-knapp.
Game over-skärm – Ett meddelande när spelaren vinner eller förlorar.
HUD (valfritt) – Exempelvis hälsobar, poäng eller en timer.
### 4. Enkla ljudeffekter och musik
Ljud för rörelse, hopp, kollisioner eller insamling.
Bakgrundsmusik – Enkel bakgrundslåt eller ljudeffekter för atmosfär.
### 5. Enkel AI eller spelelement (valfritt)
Grundläggande fienderörelse – Fiender kan patrullera eller jaga spelaren.
Samlarföremål – Mynt, kristaller eller andra objekt som ger poäng.
Enkel fysik – Gravitation, hopp eller fall när spelaren går av en plattform.
### 6. Scen- och nivåhantering
Enkla scenövergångar – Flytta mellan olika nivåer eller starta om spelet.
Respawn eller återställning – Om spelaren faller av kartan eller dör, ska spelet kunna återställa scenen.


