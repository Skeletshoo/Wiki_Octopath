---
type: region
locations:
 - "[[Le Continent]]"
tags:
 - location/generalRegion
headerLink: "[[Désert Magique#Désert Magique]]"
---

![[banner.jpg|banner]]
###### Désert Magique
<span class="sub2">:FasMap: General Region</span>
___

> [!infobox|no-t right]
> ###### Details:
> | Type | Stat |
> | ---- | ---- |
> | :FasCrown: **Aliases**   |  |
> | :RiSwordFill: **Région** |  `=this.location`|
> | **Capitale** |  `=this.subClass`|

> [!quote|no-t] SOMMAIRE
>Description of the general region Désert Magique.

## __Sur le Désert Magique__

Cet immense désert n'est pas seulement une terre aride où presque rien ne pousse, c'est aussi l'un des rares lieux où la magie est inutilisable. Ce qui le démarque des autres zones de [[Zones de Magie Morte|magie morte]], c'est sa taille. Habituellement, les effets sont restreints à quelques kilomètres carrés. Ici, c'est un bon quart du [[Le Continent|Continent]] qui y est soumis. Aucune recherche à ce jour n'a pu déterminer si cet effet est naturel, ou si quelque chose en est la cause. Des équipes sont régulièrement dépêchées sur les lieux, mais rien de concluant n'a encore été découvert.

Avant de traverser le désert, des précautions doivent être prises si vous tenez à la vie. L'emploi d'un guide est tout particulièrement conseillé, afin d'éviter les rencontres indésirables avec les nomades ou avec d'autres créatures moins sympathiques. Pour les aventuriers les plus fortunés, un [[Médicament à Magie Pour le Désert|récent médicament]] semble vous permettre de contourner partiellement les effets de la magie morte, mais son prix ne le rend pas du tout accessible au grand public.

Sur un tout autre sujet, des ruines ont été découvertes un peu partout dans le désert, mais les explorer sans avoir accès à quelconque magie serait suicidaire.

*Manuel des aventuriers, fourni dans toutes les filiales de [[La Guilde Des Aventuriers|la Guilde]]*

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
FROM "Compendium/Atlas/Le Continent/Désert Magique"
WHERE type= "locale"
SORT file.name ASC

### Histoire
TEXTE ICI

> [!note]- Évènements
>```dataview
LIST WITHOUT ID headerLink
FROM "Compendium/Lore/Events" AND [[Désert Magique]]
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
FROM "Session Notes" AND [[Désert Magique]]
SORT file.ctime DESC


### Images
```image-layout-masonry-3



```

### Références




