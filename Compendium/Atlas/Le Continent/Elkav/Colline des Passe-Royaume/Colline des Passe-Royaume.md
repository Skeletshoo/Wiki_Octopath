---
type: locale
locations:
 - "[[Elkav]]"
tags:
 - location/plains
headerLink: "[[Colline des Passe-Royaume#Colline des Passe-Royaume]]"
---

![[CollinePasseRoyaume.jpg|banner+tall]]
###### Colline des Passe-Royaume
<span class="sub2">:FasWheatAwn: Plains</span>
___

> [!infobox|no-t right]
> ###### Details:
> | Type | Stat |
> | ---- | ---- |
> | :FasCrown: **Aliases**   |  |
> | :RiSwordFill: **Région** |  `=this.location`|
> | **Capitale** |  `=this.subClass`|

Description de plains Colline des Passe-Royaume.


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

> [!example]- LIEUX - Liste
>```dataview
LIST WITHOUT ID headerLink
FROM "Compendium/Atlas/Le Continent/Elkav/Colline des Passe-Royaume"
WHERE type= "landmark"
SORT file.name ASC

### Histoire

TEXTE ICI

> [!note]- ÉVÈNEMENTS
>```dataview
LIST WITHOUT ID headerLink
FROM "Compendium/Lore/Events" AND [[Colline des Passe-Royaume]]
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
const page = dv.current().file.path;
const pages = new Set();
const stack = [page];
while (stack.length > 0) {
const elem = stack.pop();
const meta = dv.page(elem);
if (!meta) continue;
for (const inlink of meta.file.inlinks.concat(meta.file.outlinks).array()) {
const locations = dv.page(inlink.path);
if (!locations || pages.has(inlink.path) || inlink.path === meta.locations?.[0]) continue;
 if (dv.array(locations.locations).join(", ").includes(meta.file.path)) {
 pages.add(inlink.path);
 stack.push(inlink.path);
}}}
const data = Array.from(pages)
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
FROM "Session Notes" AND [[Colline des Passe-Royaume]]
SORT file.ctime DESC


### Images
```image-layout-masonry-3

```

### Références


