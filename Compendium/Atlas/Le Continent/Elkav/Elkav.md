---
type: region
locations:
 - "[[Le Continent]]"
tags:
 - location/country
headerLink: "[[Elkav#Elkav]]"
---

![[banner.jpg|banner]]
###### Elkav
<span class="sub2">:FasFlag: Country</span>
___

> [!infobox|no-t right]
> ###### Details:
> | Type | Stat |
> | ---- | ---- |
> | :FasCrown: **Aliases**   |  |
> | :RiSwordFill: **Région** |  `=this.location`|
> | **Capitale** |  `=this.subClass`|

> [!quote|no-t] SOMMAIRE
>Description of the country Elkav.


***
## __Sur [[Elkavv]]__

Peu sont ceux qui entre dans le noyau dur de cette nation. La partie centrale, en forme d'hexagone régulier, contient l'intégralité de sa population.

La délimitation de ce noyau est très marquée, car le paysage change radicalement de l'intérieur à l'extérieur. Là où la majorité du territoire d'Elkav pourrait être comparé à la topographie de [[Rybyyyy]], sa zone centrale possède un marais, une forêt de champignons ou encore de grandes montagnes.

Les habitants de ce noyau ne commercent ni ne communiquent avec les autres pays. Renfermés sur eux-mêmes, ils laissent généralement les voyageurs passer, mais là plupart ont trop peur de s'aventurer en cet endroit. On raconte que de nombreux aventuriers ne sont jamais revenus de l'intérieur des frontières.

Le reste du territoire qui est attribué à Elkav l'est en grande partie par "tradition". Depuis des temps anciens, ces terres appartiennent à ce pays, et personne n'oserait tenter de les lui reprendre. Cependant, cette zone "neutre" ne semble pas administrée par le noyau. Les aventuriers et voyageurs en quête de terres sauvages s'y aventurent donc régulièrement.

*L'__Atlas du Continent, recueil de cartes et de légendes__*


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
FROM "Compendium/Atlas/Le Continent/Elkav"
WHERE type= "locale"
SORT file.name ASC

### Histoire
TEXTE ICI

> [!note]- Évènements
>```dataview
LIST WITHOUT ID headerLink
FROM "Compendium/Lore/Events" AND [[Elkav]]
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
FROM "Session Notes" AND [[Elkav]]
SORT file.ctime DESC


### Images
```image-layout-masonry-3



```

### Références




