# 🧮 Decentralization Scoring System (v1.3)

This scoring system evaluates how decentralized and self-hostable a platform is, based on four core metrics.

## 📊 Scoring Metrics (Total: 100 Points)

| Metric                           | Weight | Description |
|----------------------------------|--------|-------------|
| **Top Provider User Share**      | 30     | Measures how many users are on the largest instance. Full points if <20%; 0 if >80%. |
| **Top Provider Content Share**   | 30     | Measures how much content is hosted by the largest instance. Full points if <20%; 0 if >80%. |
| **Ease of Self-Hosting: Server** | 20     | Technical ease of running your own backend. Full points for simple setup with good docs. |
| **Ease of Self-Hosting: User Interface** | 20     | Availability and usability of clients. Full points for accessible, FOSS, multi-platform clients. |

---

## 📋 Example Breakdown (Estimates)

| Platform   | Score | Visualization                           
|------------|-------|--------------
| 📧 Email      |    95 | 🟩🟩🟩🟩🟩🟩🟩🟩🟩🟩🟩🟩🟩🟩🟩🟩🟩🟩🟩
| 🐹 Lemmy      |    79 | 🟩🟩🟩🟩🟩🟩🟩🟩🟩🟩🟩🟩🟩🟩🟩🟩
| 🐘 Mastodon   |    74 | 🟩🟩🟩🟩🟩🟩🟩🟩🟩🟩🟩🟩🟩🟩🟩                 
| 🟣 PeerTube   |    94 | 🟩🟩🟩🟩🟩🟩🟩🟩🟩🟩🟩🟩🟩🟩🟩🟩🟩🟩🟩
| 🖼 Pixelfed   |    42 | 🟧🟧🟧🟧🟧🟧🟧🟧
| 🔵 Bluesky    |    14 | 🟥🟥🟥                                 
| 🟥 Reddit     |     3 | 🟥 

---

### 📧 Email

- **Top Provider User Share**: Google ≈ 17% → **Score: 30/30**
- **Top Provider Content Share**: Google handles ≈ 17% of mail → **Score: 30/30**
- **Self-Hosting: Server**: Easy (Can leverage hundreds of email hosting options) → **Score: 16/20**
- **Self-Hosting: Client**: Easy (Thunderbird, K-9, etc.) → **Score: 19/20**

**Total**: 95/100

---

### 🐹 Lemmy

- **Top Provider User Share**: lemmy.world ≈ 37% → **Score: 21.5/30**
- **Top Provider Content Share**: lemmy.world hosts ≈ 37% content → **Score: 21.5/30**
- **Self-Hosting: Server**: Easy (Docker, low resource) → **Score: 18/20**
- **Self-Hosting: Client**: Good FOSS apps, web UI → **Score: 18/20**

**Total**: 79/100

---

### 🐘 Mastodon

- **Top Provider User Share**: mastodon.social ≈ 40% → **Score: 20/30**
- **Top Provider Content Share**: mastodon.social ≈ 45–50% content → **Score: 20/30**
- **Self-Hosting: Server**: Docker setup, moderate difficulty → **Score: 15/20**
- **Self-Hosting: Client**: Strong ecosystem (Tusky, web, etc.) → **Score: 19/20**

**Total**: 74/100

---

### 🟣 PeerTube

- **Top Provider User Share**: wirtube.de ≈ 14% → **Score: 30/30**
- **Top Provider Content Share**: Approximately 14% → **Score: 30/30**
- **Self-Hosting: Server**: Docker, active community, moderate resources → **Score: 16/20**
- **Self-Hosting: Client**: Web-first UI, FOSS, some mobile options → **Score: 18/20**

**Total**: 94/100

---

### 🖼 Pixelfed

- **Top Provider User Share**: pixelfed.social ≈ 71% → **Score: 4.5/30**
- **Top Provider Content Share**: Approximately 71% → **Score: 4.5/30**
- **Self-Hosting: Server**: Laravel-based, Docker available, some config needed → **Score: 15/20**
- **Self-Hosting: Client**: Web UI, FOSS, mobile apps in progress → **Score: 18/20**

**Total**: 42/100

---

### 🔵 Bluesky

- **Top Provider User Share**: bsky.social ≈ 99% → **Score: 0/30**
- **Top Provider Content Share**: Nearly all content on bsky.social → **Score: 0/30**
- **Self-Hosting: Server**: PDS hosting possible but very niche and poorly documented → **Score: 4/20**
- **Self-Hosting: Client**: Mostly official client; some 3rd party → **Score: 10/20**

**Total**: 14/100

---

### 🟠 Reddit

- **Top Provider User Share**: Reddit hosts 100% of user accounts → **Score: 0/30**
- **Top Provider Content Share**: Reddit hosts all user-generated content → **Score: 0/30**
- **Self-Hosting: Server**: Not self-hostable (proprietary platform) → **Score: 0/20**
- **Self-Hosting: Client**: Some unofficial clients available → **Score: 3/20**

**Total**: 3/100

---

# How Scores are Calculated

## 🧑‍🤝‍🧑 How User/Content Share Scores Work

This measures how many users are on the largest provider (or instance).

- **No provider > 20%**: If no provider has more than 20%, it gets full 30 points.
- **Between 20% and 80%**: Anything in between is scored on a linear scale.
- **> 80%**: If a provider has more than 80%, it gets 0 points.

### 📊 Formula:
`Score = 30 × (1 - (TopProviderShare - 20) / 60)`  
…but only if TopProviderShare is between 20% and 80%.  
If below 20%, full 30. If above 80%, zero.

#### 📌 Example:
If one provider has 40% of all users:  
→ `Score = 30 × (1 - (40 - 20) / 60) = 30 × (1 - 0.43) = 17.1 points`

## 🖥️ How Ease of Self-Hosting Scores Work

These scores measure how easy it is for individuals or communities to run their own servers or use clients.

This looks at how technically easy it is to run your own **backend** (e.g., email server, Mastodon server) or **User Interface** (e.g., web-interface or mobile-app)

- **Very Easy**: One-command or setup wizard, great documentation → **18–20 points**
- **Moderate**: Docker or manual setup, some config, active community support → **13–17 points**
- **Hard**: Complex setup, needs regular updates or custom config, poor documentation → **6–12 points**
- **Very Hard or Proprietary**: Little to no self-hosting support, undocumented → **0–5 points**

---

# 📚 Sources

- **📧 Email**  
  [W3Techs – Email Server Overview](https://w3techs.com/technologies/overview/email_server)
- **🐹 Lemmy**  
  [Fedidb – Lemmy Software Stats](https://fedidb.org/software/lemmy)
- **🐘 Mastodon**  
  [Fedidb – Mastodon Software Stats](https://fedidb.org/software/mastodon)
- **🟣 PeerTube**  
  [Fedidb – PeerTube Software Stats](https://fedidb.org/software/peertube)
- **🖼 Pixelfed**  
  [Fedidb – Pixelfed Software Stats](https://fedidb.org/software/pixelfed)
- **🔵 Bluesky**  
  [SoftwareMill – Bluesky’s Decentralized Architecture](https://softwaremill.com/blueskys-decentralized-architecture-compared-to-mastodon-and-twitter-x/)
- **🟥 Reddit**  
  [Wikipedia - Reddit API Controversy](https://en.wikipedia.org/wiki/2023_Reddit_API_controversy)

## Footnotes
This is a work in progress and may contain mistakes. If you have ideas or suggestions for improvement, feel free to let me know.

Source: https://github.com/NoBadDays/decentralization-score/blob/main/decentralization_score_2025.04.md 
