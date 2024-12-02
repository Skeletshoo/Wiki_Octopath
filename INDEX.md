---
cssClasses: index
---
![[compendium.jpg|banner p+tc]]
###### <span class="head">Journal de Campagne</span> 
 
```dataviewjs
// Set path and class
const vault = this.app.vault.adapter.getResourcePath("").split("?")[0];
dv.container.className += ' hideSort cards cards-cover cards-1-1';

// Display PC card table
dv.table(["cover", "name", "details"],
  dv.pages(`"Compendium/Party/Player Characters"`)
  .sort(page => page.file.name, "asc")
    .map(p => [
      `![](${vault}/${p.cover})`, // For image link use: [![](${vault}/${p.cover})](<${p.file.name}#${p.file.name}>)
      p.headerLink,
      obsidian.Platform.isMobile ? `:FasCrown: Level ${p.level}<br>:FasUserGroup: ${p.race}<br>:RiSwordFill: ${p.class}` : `:FasCrown: Level ${p.level} / :FasUserGroup: ${p.race} / :RiSwordFill: ${p.class}`
    ])
);
```

> [!npc]-   PNJs<br><span class="sub">Personnages Non-Joueurs</span>
> `BUTTON[npc]`
> ```dataviewjs
> dv.container.className += ' listMe';
> let pages = dv.pages('"Compendium/NPC\'s"').sort(p => p.file.name, "asc");  
> dv.table(["Name"], pages.map(page => [`- ${page.headerLink}`]));
>```


> [!agenda]-  Le Groupe!<br><span class="sub">Objetifs, Joueurs et Quêtes</span>
> `BUTTON[pc]` `BUTTON[quest]`
>```dataviewjs
>dv.container.className += ' listMe';
>let tags = [];
>let pages = dv.pages('"Compendium/Party/Quests"').sort(p => p.file.name, "asc");
>dv.table(["Name", "Status"], pages.map(page => {
>const questStatusTerms = ["quest/completed", "quest/abandoned", "quest/failed", "quest/ongoing", "quest/pending"];
>let status = questStatusTerms.find(term => page.tags && page.tags.includes(term));
>status = status ? `(${status.replace("quest/", "")})` : "";
>return [`- ${page.headerLink} ${status}`, status];
>}));
>```


> [!genloc]-  Locations<br><span class="sub">Lieux, Pays et Villes</span>
>`BUTTON[plane, realm, continent, region, locale, landmark]`
> ```dataviewjs
> dv.container.className += ' listMe';
> let pages = dv.pages('"Compendium/Atlas"').sort(p => p.file.name, "asc");  
> dv.table(["Name", "Type"], pages.map(page => [`- ${page.headerLink} (${page.type})`, page.type]));
>```


> [!lore]-  Lore & Mythes<br><span class="sub">Factions, Dieux, Reliques & Plus</span> 
> `BUTTON[deity, event, object, org]`
> ```dataviewjs
> dv.container.className += ' listMe';
> let pages = dv.pages('"Compendium/Lore"').sort(p => p.file.name, "asc");  
>dv.table(["Name", "Type"], pages.map(page => [`- ${page.headerLink} (${page.type})`, page.type]));
>```

 
> [!session]-  Notes de Session<br><span class="sub">Summaries, Transcripts, & Notes</span>
> `BUTTON[note]`
> ```dataviewjs
> dv.container.className += ' listMe';
> let pages = dv.pages('"Session Notes"').sort(p => p.file.name, "desc");  
>dv.table(["Date"], pages.map(page => [`- ${page.headerLink}`]));
>```