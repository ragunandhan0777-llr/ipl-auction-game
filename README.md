# 🏏 IPL Auction Game

A mobile-first browser game where you play an IPL franchise owner: bid for players live against rival teams, use your Right to Match cards, pick a Playing XI + 4 substitutes, and top the leaderboard.

**Play it:** `https://<your-username>.github.io/ipl-auction-game/` (after enabling GitHub Pages — see below)

## Features

- **Three auctions**
  - **Mega Auction 2025:** all 182 players sold in Jeddah, ₹120 Cr purse, up to 25 players.
  - **Mini Auction 2026:** all 77 players sold in Abu Dhabi. Teams start with their real retained squads at their retention prices and their real remaining purses (KKR ₹64.3 Cr … MI ₹2.75 Cr). Each team has 2 **Right to Match** cards.
  - **Legends Auction:** 100 retired stars (Gayle, Raina, Harbhajan, DK, Dhawan …) across all 10 IPL teams.
- **Live bidding:** going once, going twice, SOLD! Computer teams bid sensibly, at most about 10% over a player's real auction value.
- **Modes**
  - Single player against 9 computer teams.
  - Pass & play: 2–9 friends on one phone.
  - Online rooms: share a lobby link, up to 9 players on their own phones.
- **Auto-bid:** hand your team to the AI any time. In pass & play, the AI also takes over a team that hasn't bid for 6 players in a row.
- **Playing XI + 4 subs:** pick them yourself or tap ⭐ Best pick.
- **Leaderboard:** podium, best pick, costliest buy, star player.
- **Share:** WhatsApp, Telegram and copy links for invites and results.
- **Graphics:** drawn player portraits and original team crests (no photos or official logos).

## Online multiplayer (lobby links)

- Tap **Host online room** to get a 6-character room code and an invite link like `https://<you>.github.io/ipl-auction-game/#join-ABC123`.
- Share the link on WhatsApp or Telegram. Friends tap it, type their name and pick a team. **No login needed.**
- Up to 9 human players; the computer plays every unclaimed team.
- If someone's connection drops, the AI bids for their team until they're back.
- The host's phone runs the auction, so the host should keep the game open and the screen on.

Rooms are relayed through a free public MQTT broker (`broker.emqx.io`, with `broker.hivemq.com` as a fallback). Messages aren't private, so don't put anything personal in your player name.

## Run locally

It's a single self-contained file. Just open `index.html` in any browser. No build step and no dependencies apart from Google Fonts.

## Publish on GitHub Pages

1. Create a new repository on GitHub named `ipl-auction-game` (Public).
2. Click **Add file → Upload files**, drag in `index.html`, `README.md` and `.nojekyll`, then **Commit changes**.
3. Go to **Settings → Pages**, set **Source: Deploy from a branch**, choose branch **main** and folder **/ (root)**, then **Save**.
4. After a minute your game is live at `https://<your-username>.github.io/ipl-auction-game/`.

Or with git:

```bash
git clone https://github.com/<your-username>/ipl-auction-game.git
cd ipl-auction-game
# copy index.html, README.md, .nojekyll into this folder
git add . && git commit -m "IPL Auction Game" && git push
```

## Data sources

- IPL 2025 mega auction sold list: The Federal
- IPL 2026 mini auction sold list: Wisden, The Federal
- IPL 2026 retentions and purses: Sportskeeda, Wisden
- Legends League Cricket 2026 squads: CricTracker

Player "values" are their real auction prices; Legends values are estimated, since individual prices weren't published.

## Disclaimer

An unofficial fan-made game, not affiliated with the BCCI, IPL, any franchise or Legends League Cricket. Team names are used for identification only; crests and player portraits are original illustrations.
