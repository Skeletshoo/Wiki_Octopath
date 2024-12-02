---
type: region
locations:
 - 
tags:
 - location/kingdom
headerLink: "[[Lumendor#Lumendor]]"
---

![[cite_doree_anato-finnstark-web-pti.jpg|banner+tall]]
###### Lumendor
<span class="sub2">:FasChessRook: Kingdom</span>
___

> [!infobox|no-t right]
> ###### Details:
> | Type | Stat |
> | ---- | ---- |
> | :FasCrown: **Aliases**   |  la Cité des Lumières |
> | :RiSwordFill: **Région** |  `=this.location`|
> | **Capitale** |  `=this.subClass`|

Description of the kingdom Lumendor.
Lumendor est lié aux [[Les Épées de Puissance]]


###### __Sur la Cité des Lumières__
<span class="sub2">:LiFlame:: Légende</span>

> [!quote|no-t]
> ![[justin-fawcett-gw546.jpg|right wm-sm]]Il est un lieu que les explorateurs n'ont cessé de chercher depuis plusieurs siècles.
> 
> [[Lumendor]], la Cité des Lumières, un royaume de magie et de prospérité. On raconte que les Lumendoriens auraient des décénies voir des siècles d'avance en matière de technologie et de maîtrise de la magie.
> 
> On s'y baigne dans la lumière, la nourriture y est abondante, on y vit comme dans un rêve.
> 
> Certains affirment que [[Lumendor]] a disparu il y a longtemps, d'autres qu'elle n'attend que d'être redécouverte. D'autres encore pensent que les [[Lumendoriens]] veillent sur le continent depuis leur citée dorée, en veillant à ce que les peuples ne s'éteignent pas.
> 
> *Contes et Légendes du Continent, par [[Mysty Starcollar]]*

### Géographie
TEXTE ICI

##### Lieux Annexes
> [!column|flex 3]
>
> > [!tip]- **Nom**
> > Description
>
> > [!faq]- **Nom**
> > Description
>
> > [!note]- **Nom**
> > Description
>
> > [!success]- **Nom**
> > Description
>
>> [!example]- Lieux - Liste
>>```dataview
LIST WITHOUT ID headerLink
FROM "Compendium/Atlas/Lumendor"
WHERE type= "locale"
SORT file.name ASC

### Histoire
TEXTE ICI

> [!note]- Évènements
>```dataview
LIST WITHOUT ID headerLink
FROM "Compendium/Lore/Events" AND [[Lumendor]]
SORT file.ctime DESC

### Figures Importantes
> [!column|flex 3]
>
> > [!tip]- **Nom**
> > Description
>
> > [!faq]- **Nom**
> > Description
>
> > [!note]- **Nom**
> > Description
>
> > [!success]- **Nom**
> > Description

> [!column|flex 3]
> > [!hint]-  PNJs
> > <input type="checkbox" id="npc"/><ul class="sortMenu"><li class="sortIcon">:RiListSettingsLine:<ul class="dropdown npcedit"><li><label for="npc" class="directLabel active">Direct Links Only</label></li><li><label for="npc" class="childLabel">Include Sub-Locations</label></li></ul></li></ul>
> >```dataviewjs
dv.container.className += ' npcDirect';
dv.list(dv.pages('"Compendium/NPC\'s"')
 .where(p => p.file.outlinks.includes(dv.current().file.link))
.sort(p => p.file.link)
.map(p => p.headerLink), 1);
>>```
>>```dataviewjs
dv.container.className += ' npcChild';
let page = dv.current().file.path;
let pages = new Set();
let stack = [page];
while (stack.length > 0) {
let elem = stack.pop();
let meta = dv.page(elem);
if (!meta) continue;
for (let inlink of meta.file.inlinks.concat(meta.file.outlinks).array()) {
let locations = dv.page(inlink.path);
if (!locations || pages.has(inlink.path) || inlink.path === meta.locations?.[0]) continue;
 if (dv.array(locations.locations).join(", ").includes(meta.file.path)) {
 pages.add(inlink.path);
 stack.push(inlink.path);
}}}
let data = Array.from(pages)
.filter(p => dv.page(p)?.type === "npc")
.map(p => dv.page(p).headerLink)
.sort((a, b) => {
if (a < b) return -1;
if (a > b) return 1;
return 0;
});
dv.list(data);


### Culture et Éléments Annexes
> [!example]- Quand sommes-nous passés là-bas ?
>```dataview
LIST WITHOUT ID headerLink
FROM "Session Notes" AND [[Lumendor]]
SORT file.ctime DESC


### Images
```image-layout-masonry-3



```

### Références




