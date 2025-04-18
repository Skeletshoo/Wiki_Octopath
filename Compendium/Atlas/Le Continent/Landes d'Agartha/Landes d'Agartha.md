---
type: region
locations:
 - "[[Le Continent]]"
tags:
 - location/generalRegion
headerLink: "[[Landes d'Agartha#Landes d'Agartha]]"
---

![[landes_agartha.jpg|banner+tall]]
###### Landes d'Agartha
<span class="sub2">:FasMap: General Region</span>
___

> [!infobox|no-t right]
> ###### Details:
> | Type | Stat |
> | ---- | ---- |
> | :FasCrown: **Aliases**   | Le Creuset des Damnés |
> | :RiSwordFill: **Région** |  `=this.location`|
> | **Capitale** |  `=this.subClass`|

Un endroit désolé. On dit que les condamnés à mort y sont envoyés. 

## __[[Sur les Landes d'Agartha]]__
A l'extrême sud du continent, par-delà une chaîne de montagne infranchissable, se trouvent les Landes d'Agartha. Un désert de cendre, désolé, où la survie relève plus de la chance que de la compétence.
Quel est cet endroit? Personne ne le sait. Depuis sa découverte il y a 50 ans, les différentes équipes d'exploration sont toutes revenues folles. Enfin, lorsqu'elles revenaient.
Les rumeurs disent même qu'on y envoie des condamnés à mort, pour les laisser mourir de fatigue et de faim, d'où le nom des Landes dans le langage populaire : Le Creuset des Damnés.

*Paragraphe extrait de l'__Atlas du Continent, recueil de cartes et de légendes__*

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
FROM "Compendium/Atlas/Le Continent/Landes d'Agartha"
WHERE type= "locale"
SORT file.name ASC

### Histoire
TEXTE ICI

> [!note]- Évènements
>```dataview
LIST WITHOUT ID headerLink
FROM "Compendium/Lore/Events" AND [[Landes d'Agartha]]
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
FROM "Session Notes" AND [[Landes d'Agartha]]
SORT file.ctime DESC


### Images
```image-layout-masonry-3



```

### Références




