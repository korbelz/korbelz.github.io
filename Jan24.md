# November Blog post

I published my first Arma: Reforger mod! <--step one for learning to work with enfusion engine :)

The was a weapon mod for a friend that wanted a 1911 that fired "Gatling gun style" I didn't have a 1911 model so I used the M9 from Reforger as a stand in model. 
Here is the mod "Bogies 1911"

https://reforger.armaplatform.com/workshop/5F0D20A88E63CAE2-Bogies_1911

Here is a clip from the twitch stream of it in action: 
https://clips.twitch.tv/SpinelessCaringDotterelDAESuppy-VTsAA0PSBpWsuZKs

#Road to Warlords 4 news

After playing around a bit with the engine I've realized that I have a hard choice to make.

Option 1: I custom code the entire mission then slowly build up the code base via crawl, walk, run mission. This will be slow but I will learn the most this way. Long-term this is the best option. 

Option 2: I use the built in Scenario_Framework by BI. This is also like its own mini game engine. This will be quicker since a lot of the backend work it already done but has a downside that I will likely "grow out of it" down the road. I could be very far/deep into making a mission only to find a brick wall because I'm developing inside a walled garden built by BI. 

The correct answer for me is...why not both? I'll likely build both at least at the crawl stage, one called crawlSF and crawlSA(stand alone). This will clearly take me a lot longer but it will maximize my learning of enfusion engine and prevent any long term roadblocks. Who knows SF might turn out to be amazing.

## finalize feature sets

these "might" change a bit in the future but I've think I have things locked down pretty well for crawl and walk stage. 

### Crawl

- Sector/trigger setup: Knowledge of player in the sector, knowledge of number of players in sector, awarding points for being in the sector, UI display for being in the sector
- Leadboard UI/display: behavioral AI(remove outliers via 1.5 IQR), award/display/track points per player, session vs lifetime stats, JSON export for web leaderboards(web reporting)
- Spawn menu: loadout/item control
- Welcome screen: info page, gameplay loop, web links
- Chat/radio comms: basic logging/filter/metering system, output chat to file(web reporting), auto mute for spam(log anomalies, web reporting)
- Anti cheat: Check pos info(log anomalies, web reporting), Check scoring info(log anomalies, web reporting)
- Rare Easter egg style self promos: building decals/billboards/forest signs. Make promo system modular with on/off flags(twitch API? only display if I'm streaming?)

### Walk

- Sectors: Ease of placement/setup in editor, size/value adjustment, shape adjustment, generate name via map/assign random name, allow sectors to "connect" for game flow, track vics per sector/assign weighted values via weapons.
- Currency: award/track player currency, awards for being "active", awards for helping capture sector.
- Store menu/UI: Select vic and spent currency, ease of use for modding/adding new items.
- Spawning vics: small time delay(parachute them in?), add backend tag/tracker for vics spawned via store(for anti-cheat), add backend hooks for repair/re-arm timers, add backend hooks for clean-up timers, dashboard/side door decals(?)
- Transport side missions: Logic for picking up NPCs and awards for dropping them off near active sector.
- Sector voting/selection: all players get basic voting value, voting value can by slightly increased via score, sector reset voting, add backend for sector JSON output(web reporting)
- anti-cheat: remove vics which are in the game without backend store tag(log driver/pilot, web reporting), auto temp banning for repeated driver/pilot logs.
- Random chance of self promo dashboard decal or radio style "ad", rare easter egg NPC chatter on side missions(self promo,twitch API? only if I'm streaming?), clan decals on sideboards(clan decal database? API?)
 
