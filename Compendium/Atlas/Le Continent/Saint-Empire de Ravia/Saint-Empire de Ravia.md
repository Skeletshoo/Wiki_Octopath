---
type: region
locations:
 - "[[Le Continent]]"
tags:
 - location/kingdom
headerLink: "[[Saint-Empire de Ravia#Saint-Empire de Ravia]]"
---

![[borisut-chamnan-artstation-1.jpg|banner+tall]]
###### Saint Empire de Ravia
<span class="sub2">:FasChessRook: Kingdom</span>
___

> [!infobox|no-t right]
> ###### Details:
> | Type | Stat |
> | ---- | ---- |
> | :FasCrown: **Aliases**   |  |
> | :RiSwordFill: **Région** |  `=this.location`|
> | **Capitale** |  `=this.subClass`|

Description of the kingdom Saint Empire de Ravia.

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
FROM "Compendium/Atlas/Le Continent/Saint-Empire de Ravia"
WHERE type= "locale"
SORT file.name ASC

### Histoire
> [!abstract] **Sur le [[Saint-Empire de Ravia]]**
> La création du Saint-Empire est très récente. C'est après la [[Seconde Guerre Sainte]] que le [[Royaume de Ravia]] absorba son voisin, le [[Royaume de Valdosta]].
> C'est [[Vyctor Cuceritor]], l'actuel dirigeant, et [[Sainteté de l'Aurore Céleste]], déclarèrent la guerre pour trahison et hérésie en [[An 832|832]].
> Neuf ans plus tard, en [[An 841|841]], après neuf mois de siège de la capitale, [[Virgil Ardere]], dirigeant de Valdosta, capitula.
> 
> Bien que [[Royaume de Valdosta|Valdosta]] était supérieur militairement, le soulèvement de sa population l'affaiblit considérablement au cours de la guerre, ce qui permit à Ravia de facilement prendre l'avantage.
> 
> *Paragraphe extrait de l'__Atlas du Continent, recueil de cartes et de légendes__*

> [!note]- Évènements
>```dataview
LIST WITHOUT ID headerLink
FROM "Compendium/Lore/Events" AND [[Saint-Empire de Ravia]]
SORT file.ctime DESC

### Figures Importantes
> [!column|flex 3]
> 
> > [!tip]- **[[Vyctor Cuceritor]]**
> > Empereur du Saint Empire de Ravia et ancien roi du royaume de Ravia.
>
> > [!tip]- **[[Sainteté de l'Aurore Céleste]]**
> > Chef de l'église de l'Aurore Céleste.
>
> > [!tip]- **[[Dӑrwyn]]**
> > Aventurier et chasseur de monstres.
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
FROM "Session Notes" AND [[Saint-Empire de Ravia]]
SORT file.ctime DESC


### Images
![[RaviaCarteAvecEchelle.png]]
```image-layout-masonry-3



```

### Références




