# 🧮 Decentralization Scoring System (v1.1)

This scoring system evaluates how decentralized and self-hostable a platform is, based on four core metrics.

## 📊 Scoring Metrics (Total: 100 Points)

| Metric                           | Weight | Description |
|----------------------------------|--------|-------------|
| **Top Provider User Share**      | 30     | Measures how many users are on the largest instance. Full points if <10%; 0 if >80%. |
| **Top Provider Content Share**   | 30     | Measures how much content is hosted by the largest instance. Full points if <10%; 0 if >80%. |
| **Ease of Self-Hosting: Server** | 20     | Technical ease of running your own backend. Full points for Docker/simple setup with good docs. |
| **Ease of Self-Hosting: User Interface** | 20     | Availability and usability of clients. Full points for accessible, FOSS, multi-platform clients. |

---

## 📋 Example Breakdown (Estimates)

| Platform   | Score | Visualization                           
|------------|-------|--------------
| 📧 Email   |    90 | 🟩🟩🟩🟩🟩🟩🟩🟩🟩🟩🟩🟩🟩🟩🟩🟩🟩🟩🟩
| 🐹 Lemmy   |    60 | 🟩🟩🟩🟩🟩🟩🟩🟩🟩🟩🟩🟩 
| 🐘 Mastodon|    55 | 🟩🟩🟩🟩🟩🟩🟩🟩🟩🟩🟩                   
| 🔵 Bluesky |    14 | 🟥🟥🟥                                 
| 🟥 Reddit  |     3 | 🟥 
       

### 📧 Email

- **Top Provider User Share**: Google ≈ 17% → **Score: 27/30**
- **Top Provider Content Share**: Google likely handles ≈ 17% of mail → **Score: 27/30**
- **Self-Hosting: Server**: Easy (Leverage email hosting services) → **Score: 18/20**
- **Self-Hosting: Client**: Easy (Thunderbird, K-9, etc.) → **Score: 18/20**

**Total**: 90/100

---

### 🐹 Lemmy

- **Top Provider User Share**: lemmy.world ≈ 37.17% → **Score: 12/30**
- **Top Provider Content Share**: lemmy.world likely hosts ~37% content → **Score: 12/30**
- **Self-Hosting: Server**: Easy (Docker, low resource) → **Score: 18/20**
- **Self-Hosting: Client**: Good FOSS apps, web UI → **Score: 18/20**

**Total**: 60/100

---

### 🐘 Mastodon

- **Top Provider User Share**: mastodon.social ≈ 42.7% → **Score: 11/30**
- **Top Provider Content Share**: mastodon.social ≈ 45–50% content → **Score: 10/30**
- **Self-Hosting: Server**: Docker setup, moderate difficulty → **Score: 15/20**
- **Self-Hosting: Client**: Strong ecosystem (Tusky, web, etc.) → **Score: 19/20**

**Total**: 55/100

---

### 🔵 Bluesky

- **Top Provider User Share**: bsky.social ≈ ~90%+ (very centralized) → **Score: 0/30**
- **Top Provider Content Share**: Nearly all content on bsky.social → **Score: 0/30**
- **Self-Hosting: Server**: PDS hosting possible but very niche → **Score: 4/20**
- **Self-Hosting: Client**: Mostly official client; some 3rd party → **Score: 10/20**

**Total**: 14/100

---

### 🟠 Reddit

- **Top Provider User Share**: Reddit hosts all user accounts = 100% → **Score: 0/30**
- **Top Provider Content Share**: Reddit hosts all user-generated content → **Score: 0/30**
- **Self-Hosting: Server**: Not self-hostable (proprietary platform) → **Score: 0/20**
- **Self-Hosting: Client**: Some unofficial clients available → **Score: 3/20**

**Total**: 3/100

---

# How Scores are Calculated

## 🧑‍🤝‍🧑 How User/Content Share Scores Work

This measures how many users are on the largest provider (or instance).

- **100% (one provider)**: If one provider has all the users, it gets 0 points.
- **No provider > 10%**: If no provider has more than 10%, it gets full 30 points.
- **Between 10% and 80%**: Anything in between is scored on a linear scale.
- **> 80%**: If a provider has more than 80%, it gets 0 points.

### 📊 Formula:
`Score = 30 × (1 - (TopProviderShare - 10) / 70)`  
…but only if TopProviderShare is between 10% and 80%.  
If below 10%, full 30. If above 80%, zero.

#### 📌 Example:
If one provider has 40% of all users:  
→ `Score = 30 × (1 - (40 - 10) / 70) = 30 × (1 - 0.43) = 17.1 points`

## 🖥️ How Ease of Self-Hosting Scores Work

These scores measure how easy it is for individuals or communities to run their own servers or use clients.

This looks at how technically easy it is to run your own **backend** (e.g., email server, Mastodon server) or **User Interface** (e.g., web-interface or mobile-app)

- **Very Easy**: One-command Docker, low resources, great documentation → **18–20 points**
- **Moderate**: Docker or manual setup, some config, active community support → **13–17 points**
- **Hard**: Complex setup, needs regular updates or custom config (e.g. DNS, spam) → **6–12 points**
- **Very Hard or Proprietary**: Little to no self-hosting support, undocumented → **0–5 points**
