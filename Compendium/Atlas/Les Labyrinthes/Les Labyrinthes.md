---
type: continent
locations:
 - 
tags:
 - 
headerLink: "[[Les Labyrinthes#Les Labyrinthes]]"
---

![[banner.jpg|banner]]
###### Les Labyrinthes
<span class="sub2">:FasEarthAmericas: Continent</span>
___

> [!quote|no-t]
>Quick description of the continent Les Labyrinthes.

***
## __Sur les Labyrinthes__

Les Labyrinthes sont des structures semblant extérieures à notre réalité. Ils se composent de dédales sombres, dans lesquels se trouvent monstres, pièges et trésors.
Cependant, il semblerai que cet endroit servi jadis à d'autres desseins. En effet, si vous survivez assez longtemps dans un Labyrinthe, peut-être tomberez-vous sur une maison, ou un jardin. Petit havre de paix, ces endroits servants aujourd'hui de relais aux aventuriers tendent à nous informer qu'une certaine société vécu sans doute ici il y a longtemps.

Quoi que fût cette dimension, il semblerait qu'elle eut été coupé de la notre à une certaine époque et a été redécouverte il y a environ 3 siècles, lorsque des portes tout à fait ordinaire se mirent à s'ouvrir sur le Labyrinthe. Depuis, des aventuriers se précipitent à l'intérieur dans l'espoir d'obtenir richesse ou renommée, mais ils reviennent souvent la queue entre les jambes après une déconvenue avec un monstre local.

Encore aujourd'hui, les Labyrinthes sont des endroits méconnu, à peine cartographiés, que nous conseillons à tout aventurier, même chevronné, d'éviter à tout prix.

*Manuel des aventuriers, fourni dans toutes les filiales de [[La Guilde Des Aventuriers|la Guilde]]*
***

#### marker
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
> 
>> [!example]- LIEUX
>>```dataview
LIST WITHOUT ID headerLink
FROM "Compendium/Atlas/Les Labyrinthes"
WHERE type= "region"
SORT file.name ASC
>
>> [!note]- HISTOIRE
>>```dataview
LIST WITHOUT ID headerLink
FROM "Session Notes" AND [[Les Labyrinthes]]
SORT file.ctime DESC
#### marker