# Red & Gold Golf

A 3D, Chaminade-themed golf game that runs in any browser. Everything is in one file, index.html, with no install and no build step.

Play it at https://chamigolf.github.io/

## How to play

- Check PIN at the top for yards to the hole, then pick a club. Tap the club name to open your bag, or use the arrow buttons.
- Swipe left or right to aim. MAP shows the whole hole, and you can tap it to aim.
- Press the ball and pull back. Every shot works like putting: the tag next to the ball shows your swing % (100% = the club's full distance) with a rough distance guide underneath.
- Let go in the bright gold zone for a perfect strike.
- Putting: aim exactly with the ◀ AIM ▶ buttons in the bottom-left corner (hold to keep turning) or the left/right arrow keys (Shift = bigger steps; up/down arrows change club). Wind never moves a putt (it barely touches little chips either).
- Momentum: 3 holes in a row with no bogey adds +20% to hole payouts, then +20% more per hole you keep it going, with no limit. A bogey ends it.
- Rough cuts distance 15% and sand cuts it 40% (less with the Sand Wedge). Watch the wind arrow.
- Water and out of bounds cost a stroke. Cart paths are concrete: the ball kicks up and skips off them.
- Left-handed? Switch hands in the Golfer tab.
- Golf ball colours are free: pick a preset or mix any colour with the R/G/B sliders in Golfer > Ball (alignment lines still cost money).
- On the first tee, Mr. Haslbaur (3C Par Three) and Mr. Garner (Chami Links Crimson) pop up in the bottom-left corner with a word of encouragement (tap to dismiss; they leave after your tee shot).
- Play Friends: adding a friend is two-way, and if your friend code doesn't load there's a Try again button.
- Hole payouts: hole-in-one $1,500 · albatross $1,000 · eagle $250 · birdie $100 · par $25 · bogey or worse $0.

## Courses

3C Par Three (where everyone starts) → Chami Links Crimson (6 holes) → Chami Links Gold (Bethpage Black's front nine, 9 holes) → Chami Links Black (all 18 holes of Bethpage Black, the hardest course), plus TPC Saragosa, Farbor Lake, Meribah Country Club, Brothers Hollow and Deans Valley (its 18th hole is Room 23), Gold Star Mini Golf and the Daily Closest to the Pin.

## Clubs and upgrades

- Each club has three upgrades, up to level 5 each: Power (+4% distance), Accuracy (+1.6% gold zone, and misses 8% straighter) and Control (needle 12% slower). Levels cost $400 / $900 / $1,800 / $3,500 / $6,000 (Power 20% more). A stat can only go one level past the club's lowest stat.
- Lots of club models to buy in every slot, and club colours (buy a colour once, paint any club).

## Online

- Daily Tournaments for every course, mini golf and Closest to the Pin. No sign-in needed to post: you just need a name (anyone still called "Player" is asked for one).
- Sign in with Google to save progress to the cloud and play friends.
- Premium badges (Creator's Pick, Daily Champion, Hole in One) show next to your name on the leaderboards. Only the Creator's Pick tile shows how many golfers have it. Creator's Pick goes to golfers who helped make the game or had a suggestion added.
- Unlockable outfits: the Senior Sweater (within 10 feet in the Daily Closest to the Pin) and the Masters Outfit (par or better at Chami Links Black).
- Reloaded mid-round? Keep playing, finish the round early (paid for the holes you played), or quit.

## Play Friends

- Sign in, share your 6-character friend code, and add friends by theirs (or send an invite link).
- **1v1**: stroke play for a wager ($0 up to what you have), 3, 6 or 9 holes. Tied? Sudden-death playoff holes.
- **2v2**: scramble, alt shot or best ball. **Foursome**: own ball (1v1v1v1, up to 4 golfers, lowest total wins the pot) or a 2 v 2 scramble. The host sets one buy-in that every golfer pays; a pop-up confirms it when you join, and you can't join without enough money.
- Everyone gets the same wind. Winners split the pot. Quitting a match forfeits it for your team.

## Anti-cheat and creator tools

- The game catches edited saves, money or gear it never paid out, impossible rounds and absurd drives. Strong signs ban the device right away; smaller ones are flagged.
- Flagged for review: **every hole in one** (with the golfer's career ace count, the club, the swing and the card so far), albatrosses, hole-outs from 120+ yds, 75+ ft putts, low rounds, 2+ aces / 3+ eagles / 3+ chip-ins in a round, rounds played too fast, 90%+ PERFECT swings in a round or 25 in a row, and shots that fly far past the club's distance.
- Outside interference is flagged too: taps or keys made by a script (auto-clickers), the same pull-back or hold time over and over (macros), an automated browser, built-in browser functions swapped out (rigged random numbers, speed hacks), the game clock running faster than real time, scripts/frames/extensions injected into the page, the game open in two tabs, and the save edited from another tab.
- Flags made before the game is online wait in a queue and are sent once it connects.
- Banned golfers are taken off **every** leaderboard: their scores are deleted (all-time, the last week of daily tournaments and Closest to the Pin) and a small banned list (`meta/bannedList`) hides them from every board, the tournament leaders and the prize payouts. Their holes in one are hidden too. This also cleans up auto-bans whenever the creator tools are opened.
- Scorecards: the game keeps each golfer's last 15 scorecards. An auto-ban sends them up with the ban, and a golfer banned by the creator sends theirs the next time their game checks in. In the creator tools, 📋 shows any golfer's scorecards (from the ban, their flags and Google cloud saves).
- Money: every payout goes through the game's ledger. $5,000+ showing up in the bank at once (or in total) that the game didn't pay out is an automatic ban, and so is a bank bigger than everything the golfer has ever earned. The Firebase rules enforce the same limit on cloud saves.
- The creator's account (🛡️ button on the home screen) has Find a player (search by name, give or take back Creator's Pick 🎁, ban), 🎯 Holes in one (every ace from the last 3 days with each golfer's career total, 📋 scorecards, ban), cheat flags (filters for aces, interference and money; 📋 scorecards), bans/unbans (with 📋 scorecards) and the leaderboards (remove a score, ban, 🎁).
- Money flags for review (not bans): earning over $25,000 in an hour, a bank above everything ever earned, and friends-match pots of $5,000+ or won by forfeit. Player counts, players online and rounds played are in Google Analytics.

## Updates and pop-ups

- To announce an update to players, edit `NEWS_VER` and the `NEWS` list in index.html. Each golfer sees it once. Only list things players can see (nothing about anti-cheat or creator tools).
- New players get a welcome pointing them to the 3C Par Three, plus one-time tips the first time they open Clubs and Golfer.

## Firebase free plan

The game is built to stay on the free Spark plan (50,000 reads and 20,000 writes a day; on Spark Firebase never charges, it just pauses online features until midnight Pacific if a limit is hit):

- Cloud saves (Google sign-in) go up only when a round ends, after buying something or collecting winnings, and when the game is closed. The device always saves instantly.
- Leaderboards are remembered for 5 minutes, even through a reload. Your own new score is added to the remembered board instead of downloading it again, and posting skips the "current best" lookup.
- Today's tournaments card only loads when someone taps "See today's leaders" (then it's remembered for 10 minutes).
- Today's holes-in-one are one record per day (the creator tools read the last 3 days).
- The banned list is one record (1 read per visit, remembered for 30 minutes).
- The Creator's Pick count loads once per visit; the ban check runs every 15 minutes.
- Play Friends invites are only watched on the home screen (newest 10). Stroke play and best ball send one score per hole; scramble and alt shot send every shot because players take turns.
- No "last seen" notes or daily counters: those stats come from Google Analytics.
- The creator's Find a player search uses a tiny player directory: one record per golfer, written only when they first pick a name or change it.

## Google Analytics

On, with Measurement ID `G-4D02FQ9XMJ` (`GA_ID` in index.html). Players online, players per day, new players, rounds started and finished, aces and Closest to the Pin shots show up in Google Analytics (Firebase console > Analytics, or analytics.google.com). It's free and doesn't count against Firebase's database limits.

## Firebase setup

1. Publish the rules in `firestore.rules` (Firebase console > Firestore Database > Rules > Publish). The Oct 20 2026 update added `meta/bannedList` (the banned list that hides banned golfers from every board), so publish them again.
2. Turn on guest sign-in: Firebase console > Authentication > Sign-in method > **Anonymous** > Enable. (Without it, only Google-signed-in players can post scores.)

ChamiCards will be back.

## License

MIT
