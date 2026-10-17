# 🍿 Popcorn

**Find your watch, find your people.**

Popcorn is a taste-matching and watch-together app for movie and TV lovers. It builds a taste profile from a short personality quiz, recommends what to watch, connects you with people who like what you like, and helps friend groups decide what to watch together.

Built with **Base44** for the Base44 app-building challenge.

🔗 **Live app:** [ADD YOUR BASE44 APP LINK HERE]
🎥 **Demo video:** [ADD LINK IF AVAILABLE]

---

## The problem

- Movie recommendations are generic and ignore who you are and how you feel right now.
- Choosing something to watch with friends turns into a 30-minute argument.
- Streaming platforms do not connect their viewers, and none of them works across services.

## Who it helps

- Movie and series lovers who are not sure what to watch next
- Friend groups and college movie clubs
- Long-distance friends who want a shared watch night
- People who want to find others with similar taste

## How Popcorn is different

| | Typical movie sites | Popcorn |
|---|---|---|
| Starting point | You already know your taste | A fun personality quiz builds it for you |
| Recommendations | Browse and search | AI-ranked picks with a "why this fits you" line |
| Mood | Ignored | A "Mood changed?" check-in refreshes picks for tonight |
| Group decisions | Not supported | "Start a Popcorn Night" suggests titles everyone will enjoy |
| Relationships | Follower counts | Synergy score and tiers between friends |

---

## Features

### 1. Personality quiz and taste profile
Eight short questions map answers to genre weights, moods, runtime preferences and dealbreakers. The result is a taste profile and a shareable archetype such as "Slow-Burn Thriller Soul".

### 2. Hybrid recommendation engine
1. **Scoring:** each unseen title is scored on genre match, mood match, quality, platform availability and language.
2. **AI re-rank:** the top candidates go to an AI model that returns the best 10 with a one-line reason for each and genre variety.
3. **Learning:** ratings gradually adjust the taste profile.
4. **Fallback:** if the AI call fails, the score-ranked list is shown with a template reason.

### 3. "Mood changed?" check-in
A 5-question, under-30-seconds check-in creates a temporary mood layer (blended 60% mood, 40% long-term taste) and refreshes the picks. It expires after 6 hours and never overwrites the permanent profile.

### 4. Genre communities
Join communities such as Comedy, Thriller, Anime, Sci-Fi, Romance, Drama, Bollywood and K-Drama. Each includes:
- Feed with posts, reactions, threaded comments and spoiler toggles
- Group chat with channels (including a spoiler zone)
- Rate & Rank leaderboards
- Polls, events and a Title of the Week
- Member list, badges and moderation tools

### 5. Friends and recommendations
Add friends, see your taste-match %, and send title recommendations that arrive as in-app notifications.

### 6. Synergy score and tiers
Friendship strength grows as you watch together.

| Action | Points |
|---|---|
| Title watched together | +10 |
| Both ratings within 1 star | +5 |
| Accepted recommendation | +2 |

| Tier | Score |
|---|---|
| Kernel | 0 to 24 |
| Popping | 25 to 59 |
| Buttered | 60 to 99 |
| Caramel Soulmates | 100+ |

### 7. Start a Popcorn Night (Watch Together)
1. Start a session and invite friends or community members.
2. Members join.
3. The app combines everyone's taste using `group_score = 0.6 × average + 0.4 × minimum`, so nobody gets a title they would hate.
4. The top 3 are shown with a reason for each. Members vote and the winner is announced.
5. The creator schedules the date, time and platform, and reminders are sent.
6. After watching, members rate and synergy scores update.

---

## How Base44 is used

Base44 is the core of the project: the app, backend and AI features are built through Base44.

| Area | Base44 capability used |
|---|---|
| App building | Built and refined through prompt-driven iteration in Base44 chat |
| Authentication | Built-in sign up, login and user profiles |
| Database | Entities for users, titles, ratings, communities, posts, chat messages, friendships, recommendations, synergy pairs, watch sessions, votes and notifications |
| Backend logic | Backend functions for scoring, taste matching, synergy updates and group scoring |
| AI | AI integration for archetype names, mood names, re-ranking and "why this fits you" reasons |
| Notifications | In-app notifications and email reminders for watch nights |
| Configuration | `QUIZ_MAP`, `MOOD_MAP` and `ENGINE_WEIGHTS` stored as editable JSON so weights can be tuned without code changes |

**Build process:** [ADD NUMBER] chat iterations. The app was built in stages: entities and auth, quiz, recommendation engine, friends and synergy, communities, Watch Together, mood check-in, then seed data and polish.

---

## Data sources

Titles come from [The Movie Database (TMDB)](https://www.themoviedb.org/): title, genres, year, poster, overview, rating and language. A one-time import of roughly 150 titles is stored in the app, so recommendations do not depend on live API calls.

> This product uses the TMDB API but is not endorsed or certified by TMDB.

Streaming availability data is provided via JustWatch through TMDB.

---

## Demo flow (2 minutes)

1. Sign up and answer the personality quiz.
2. View AI-picked recommendations with reasons.
3. Tap **Mood changed?** and watch the picks refresh.
4. Join a genre community, chat and rate a title.
5. Check a friend's synergy score and tier.
6. Start a Popcorn Night, vote, and see the winning pick.

**Demo accounts:** [ADD DEMO LOGIN DETAILS IF APPLICABLE]

---

## Privacy and safety

- Private ratings and reviews are visible only to accepted friends.
- Mood check-ins and direct messages are private.
- Spoiler content is hidden by default.
- Communities include reporting, moderation roles and rate limits.

---

## Project structure

This repository documents a Base44-hosted app. The app itself runs on Base44.

```
popcorn/
├── README.md
├── docs/
│   ├── base44-prompt.md      # Master build prompt
│   ├── quiz-map.json         # Quiz questions and genre weights
│   └── screenshots/          # App screenshots
└── LICENSE
```

---

## Roadmap

- Watch history import
- Mobile push notifications
- Collaborative watchlists
- Expanded catalog and regional content
- Smarter taste learning from community activity

---

## Author

**[ASHUTOSH KHARE]**
[GitHub](https://github.com/ashu07khare-coder) 

## License

[MIT](LICENSE) or choose your preferred license.
