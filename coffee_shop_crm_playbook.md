# BeanFlow CRM: Coffee Shop Playbook
*A Complete End-to-End Product Management Lifecycle Execution*

This document showcases the execution of the **Ultimate AI PM Mega Prompt** for **BeanFlow CRM**, an intelligent loyalty and customer relationship management system designed specifically for independent coffee shops.

---

## Workspace & Product Configuration

* **MY PRODUCT / IDEA**: **BeanFlow CRM** — A mobile-first CRM and smart loyalty system that helps independent coffee shops automate personalized promotions, track customer visit patterns, and run digital stamp cards without requiring expensive POS integrations.
* **MY TARGET USER**: Independent coffee shop owners and store managers who want to increase repeat visits but find enterprise POS systems (like Toast or Lightspeed) too expensive or complex.
* **MY MARKET**: Food & Beverage (F&B) Retail SaaS / SMB CRM & Loyalty.
* **MY STAGE**: Idea / Pre-launch.

---

# PHASE 1 — DISCOVER

### [1A] HYPOTHESIS
**Falsifiable Product Hypothesis:**
> "We believe **independent coffee shop owners** have a problem with **low customer retention rates and a lack of direct marketing channels** when relying on paper punch cards. We will know this is true when **at least 15% of active coffee shop customers download the BeanFlow loyalty app and redeem their first digital reward within 30 days of shop onboarding**."

**The 3 Riskiest Assumptions:**
1. **Desirability (Owners)**: Shop owners are willing to display QR codes and train baristas to promote a digital loyalty system instead of using traditional paper punch cards.
2. **Friction (Customers)**: Customers will take the 10 seconds to scan a QR code at the register rather than just paying and walking away.
3. **Integration (POS)**: Independent shops can run this standalone on a tablet next to their existing register without needing deep integration into their legacy POS (Clover, Square, etc.).

**Fastest, Cheapest Validation Tests:**
* *For Assumption 1 (Owners)*: **5 User Interviews** with local coffee shop owners. Show them a paper wireframe of the merchant dashboard and ask: "If we gave you this dashboard for free for 3 months, would you print this QR code stand and put it next to your credit card reader?"
* *For Assumption 2 (Customers)*: **Fake Door Test**. Put a printed acrylic stand at a friendly local shop saying: "Scan to get your 10th coffee free (Digital Loyalty Beta)." Track how many scans the QR code gets relative to daily customer volume.
* *For Assumption 3 (Integration)*: **Concierge MVP**. Run a 1-week test where we manually send SMS reward coupons to 20 customers of a single shop using a Google Sheet to track punches, proving the system works without POS software.

**Go/No-Go Criteria:**
* **Kill Criteria**:
  - Less than 5% scan rate during the Fake Door Test.
  - Owners state they will only use a loyalty tool if it is deeply integrated directly into their existing POS interface.
* **Green Light Criteria**:
  - >12% scan rate in the Fake Door Test.
  - At least 3 out of 5 interviewed owners agree to run a 30-day live pilot in their shops.

---

### [1B] MARKET LANDSCAPE

#### Top 5 Competitors
1. **Square Loyalty**: 
   - *Pricing*: Add-on starting at $45/month per location.
   - *Strengths*: Seamlessly built into the widely-used Square POS; zero friction for existing Square merchants.
   - *Weaknesses*: Expensive for small shops; only works if the shop uses Square POS.
2. **Candybar.co**:
   - *Pricing*: $45/month flat rate.
   - *Strengths*: Simple web-based loyalty tracker; does not require POS integration.
   - *Weaknesses*: Lacks automated marketing tools (like SMS or automated email campaigns).
3. **Loyera**:
   - *Pricing*: Freemium up to 50 customers, then $19/month.
   - *Strengths*: Low cost; simple merchant app.
   - *Weaknesses*: Outdated UI/UX; poor customer-facing experience.
4. **Toast Loyalty**:
   - *Pricing*: Add-on starting at $50/month per location.
   - *Strengths*: Powerful, deeply integrated restaurant CRM; supports online ordering.
   - *Weaknesses*: Restricted only to restaurants using Toast hardware; completely unavailable to independent shops using other registers.
5. **Traditional Paper Punch Cards**:
   - *Pricing*: ~$0.05 per card (printing costs).
   - *Strengths*: Zero technology friction; universally understood.
   - *Weaknesses*: No data collection, zero customer insights, high fraud rate, frequently lost by customers.

#### Strategic Gaps & Entry Angle
* **The Single Biggest Gap**: A loyalty system that provides **automated SMS re-engagement campaigns** (e.g., "We haven't seen you in 4 days, here is 20% off your next Latte") *without* requiring the merchant to swap out their cash register or POS system.
* **18-Month Trends**: High adoption of mobile wallets (Apple Wallet/Google Pay loyalty passes) and the rise of localism post-inflation, where consumers want to support independent shops but expect Starbucks-level digital experiences.
* **Entry Angle (How We Win)**: We launch **"Scan-to-Wallet" passes**. Customers scan a QR code at the register, and a loyalty card instantly goes into their Apple or Google Wallet. No app download is required for the customer. Merchants manage everything from a simple Android/iOS tablet app sitting next to their register.

---

### [1C] USER PERSONAS

#### Persona 1: Sarah, 38 — The Independent Owner
* **Demographics**: Owner of "The Daily Grind" (2 locations), Income: $72,000/year.
* **Primary Goal**: Increase the frequency of casual customers from 1.2 visits/week to 2.5 visits/week.
* **Top 3 Frustrations**:
  - Customers lose paper cards and complain.
  - Square POS charges too much for loyalty add-ons.
  - Has no way to contact customers once they walk out the door.
* **Behaviors**: Busy, works the register during rush hours, relies heavily on Instagram for marketing.
* **Direct Quote**: *"I know half my customers by face, but I have no idea how many of them actually come back every week, or how to get them back when business is slow."*
* **Key Feature**: Automated SMS campaign builder for slow weekdays.

#### Persona 2: Elena, 24 — The Head Barista
* **Demographics**: Head Barista, Income: $32,000/year.
* **Primary Goal**: Keep checkout transaction times under 30 seconds during the morning rush.
* **Top 3 Frustrations**:
  - Customers searching their bags for paper punch cards while the line backs up.
  - Complex software that takes too many taps to add a point.
  - Customers arguing about how many points they should have.
* **Behaviors**: Tech-savvy, values fast workflows, gets stressed by long lines.
* **Direct Quote**: *"If a loyalty app takes more than 5 seconds to scan at the counter, I'm not going to suggest it to customers when I have a line out the door."*
* **Key Feature**: Ultra-fast QR scanning screen with sound/haptic validation.

#### Persona 3: David, 29 — The Remote Worker (Customer)
* **Demographics**: Software Engineer, Income: $105,000/year.
* **Primary Goal**: Get rewarded for his daily coffee run without carrying physical cards.
* **Top 3 Frustrations**:
  - Forgotten punch cards sitting at home.
  - Downloading a separate app for every coffee shop he visits.
  - Spammy marketing notifications.
* **Behaviors**: Pays exclusively with his phone, works from cafes, loyal to 2-3 local spots.
* **Direct Quote**: *"I love supporting local cafes, but if I have to download a 50MB app just to track my coffee points, I'll pass."*
* **Key Feature**: Apple Wallet & Google Pay pass integration.

---

# PHASE 2 — DEFINE

### [2A] METRICS FRAMEWORK

#### North Star Metric
* **Weekly Active Loyals (WAL)**: The number of unique customers who scan their loyalty card at least **twice** in a 7-day period at a participating shop.
* *Why?* Loyalty systems succeed only if they drive repeat habit-forming behaviors. Single scans don't prove retention. Two visits a week indicates the shop is becoming a routine.

#### Input Metrics
1. **Onboarding Rate (Customer)**: % of scans that result in a customer adding the pass to their Apple/Google Wallet.
2. **Scan Velocity (Barista)**: Average time (in seconds) between customer presenting their pass and scanner confirmation.
3. **Redemption Rate**: % of earned rewards that are actually claimed by customers.
4. **Active Merchant Rate**: % of registered shops that record at least 50 loyalty scans per week.

#### Health & Guardrail Metrics
1. **Checkout Latency**: If the average transaction checkout time increases by >5 seconds due to scanning, checkout friction will kill merchant adoption.
2. **Opt-Out Rate**: % of customers who block SMS alerts or delete their wallet passes.
3. **Merchant Churn**: % of shops that uninstall the app or cancel subscriptions monthly.

#### Vanity Metrics to AVOID
1. **Total Registered Users**: Looks good on paper but ignores churned users who deleted the pass after one scan.
2. **App Store Downloads (Merchant App)**: Merchants downloading the app does not translate to customers using the system.
3. **Total Points Issued**: Points are a liability until redeemed; high points with low redemptions show a dead community.

#### Metrics Tree
```
Weekly Active Loyals (WAL)
├── Active Merchants (Shops with >= 50 scans/week)
│   ├── Merchant Retention Rate
│   └── Barista Scan Rate (% of transactions scanned)
└── Repeat Customer Scans
    ├── New Wallet Passes Installed
    │   ├── Landing Page QR Scans
    │   └── Wallet Installation Conversion Rate
    └── Re-engagement CTR
        ├── Automated SMS Delivery Rate
        └── SMS Link Click-Through Rate
```

#### Day 1 Events to Instrument
1. `merchant_account_created` (Properties: `shop_name`, `country`, `pos_type`)
2. `wallet_pass_installed` (Properties: `platform_ios_android`, `shop_id`)
3. `loyalty_point_accrued` (Properties: `shop_id`, `points_added`, `barista_id`)
4. `reward_redeemed` (Properties: `shop_id`, `reward_type`, `points_spent`)
5. `reengagement_sms_sent` (Properties: `campaign_type`, `customer_id`)

---

### [2B] PRODUCT REQUIREMENTS DOCUMENT (PRD)

#### 1. Problem Statement
Small, independent coffee shops lose customer retention to large chains (like Starbucks) because they cannot afford custom mobile apps or complex loyalty database systems. Paper punch cards fail to capture customer contact info, are frequently lost, and are subject to barista fraud.

#### 2. Goals & Non-Goals
* **Goals (30/60/90 Days)**:
  - *30 Days*: Launch MVP merchant tablet app and Apple/Google Wallet pass generator.
  - *60 Days*: Onboard 15 local pilot cafes; achieve a 20% wallet pass install rate among their customers.
  - *90 Days*: Launch first automated SMS re-engagement campaign feature; hit a 15% return rate for lapsed users.
* **Non-Goals**:
  - Building a customer-facing native app (we use native Apple/Google Wallet).
  - Processing card payments directly (we sit parallel to the POS).

#### 3. Success Metrics
* North Star: **Weekly Active Loyals (WAL)** > 1,500 by Month 3.
* Merchant Net Promoter Score (NPS) > 60.

#### 4. User Stories

| Story ID | User Story | Priority | Acceptance Criteria |
|---|---|---|---|
| **US-01** | As a barista, I want to scan a customer's digital pass using a tablet camera so that I can award points in under 3 seconds. | P0 | - Scanner must launch in < 1 sec.<br>- Play a distinct success tone.<br>- Increase customer point balance instantly in the local database. |
| **US-02** | As a customer, I want to scan a receipt QR code to install the loyalty pass directly into Apple/Google Wallet. | P0 | - QR redirect must open mobile-friendly landing page.<br>- "Add to Apple Wallet" button must generate a secure `.pkpass` file. |
| **US-03** | As an owner, I want to define my shop's reward threshold (e.g., 10 points = Free Coffee) from a settings page. | P0 | - Input validation prevents zero or negative thresholds.<br>- Changes update all active customer passes in real-time. |
| **US-04** | As an owner, I want to view a daily dashboard of total scans, new members, and rewards claimed. | P1 | - Data must load in < 2 sec.<br>- Display comparisons to the previous week's performance. |
| **US-05** | As the system, I want to automatically send an SMS to customers who haven't visited in 7 days to offer a discount. | P1 | - Check daily for inactive profiles.<br>- Do not send SMS if user opted out.<br>- Include a unique tracking code. |

#### 5. Technical Considerations
- **Offline Mode**: If the shop's Wi-Fi drops, the merchant scanner must queue scans locally and sync to the cloud once connection is restored.
- **Pass Syncing**: Real-time push notifications are sent to update the point balances displayed on the customer's lock screen.

#### 6. Edge Cases & Risks

| Risk / Edge Case | Severity | Mitigation Strategy |
|---|---|---|
| Customer scans the same QR code multiple times to cheat points. | **High** | Generate dynamic, single-use checkout QR codes on the merchant tablet. |
| No internet connection during peak rush. | **Medium** | Store transactions in local IndexedDB; sync asynchronously in the background. |
| User deletes the Wallet Pass. | **Low** | Send an SMS notification offering a recovery link to reinstall the pass. |

#### 7. Open Questions
- Will Apple/Google charge registration fees for issuing Wallet Passes at scale? *(Assumed: No, standard developer account covers pass signing certificates)*.

---

### [2C] FEATURE PRIORITIZATION (RICE)

#### Feature List
1. **Wallet Pass Generator (iOS/Android)**
2. **Barista Tablet Scanner App**
3. **Admin Settings Dashboard**
4. **Automated SMS Re-engagement Engine**
5. **Dynamic QR Code Display (Anti-Fraud)**
6. **Customer Web Portal (Pass Management)**

#### RICE Matrix

| Feature | Reach (Monthly) | Impact (0.25-3) | Confidence (%) | Effort (Weeks) | RICE Score | Rank |
|---|---|---|---|---|---|---|
| **1. Wallet Pass Generator** | 10,000 | 3.0 | 100% | 4 | **7,500** | **1** |
| **2. Barista Tablet Scanner** | 8,000 | 3.0 | 90% | 3 | **7,200** | **2** |
| **3. Admin Settings** | 500 | 1.5 | 100% | 2 | **375** | **5** |
| **4. SMS Engine** | 3,000 | 2.0 | 80% | 3 | **1,600** | **3** |
| **5. Dynamic QR (Anti-Fraud)** | 8,000 | 1.0 | 50% | 3 | **1,333** | **4** |
| **6. Customer Web Portal** | 1,000 | 0.5 | 80% | 4 | **100** | **6** |

**Recommendation to Ship in Sprint 1**:
Features **1 (Wallet Pass Generator)**, **2 (Barista Scanner)**, and **3 (Admin Settings)**. These constitute the absolute Minimum Viable Product (MVP) needed to launch a live test.

---

### [2D] COMPETITOR TEARDOWN: SQUARE LOYALTY

#### 1. Onboarding Flow
- *Steps*: Merchant enables the add-on in Square Dashboard -> Customer types their phone number on the customer-facing checkout screen -> Confirm via SMS link.
- *Friction*: Typing a phone number on a physical terminal screen while a line forms behind you creates significant social pressure.
- *Aha Moment*: The instant SMS receipt confirming the customer has earned their first point.

#### 2. Retention Loops
- Automated reminder text messages sent when points are near a reward milestone.
- Integrates directly with Square Email Marketing.

#### 3. Monetization
- $45/location/month flat subscription. This eats into the margins of tiny shops doing less than $10k/month in revenue.

#### 4. Weakness to Exploit
Square requires merchants to use their POS. If a boutique shop uses another checkout method, cash, or a different processor, they cannot access Square Loyalty. **BeanFlow wins by being hardware and payment-method agnostic.**

#### 5. Competitive Playbook
- *What we steal*: The simple phone number/SMS confirmation logic for onboarding.
- *What we do differently*: We bypass checkout terminal typing by using a simple **Scan-to-Wallet** QR pass, transferring the input friction to the customer's own smartphone.

---

# PHASE 3 — BUILD

### [3A] USER STORIES + ACCEPTANCE CRITERIA (MVP Top 3)

#### Feature 1: Wallet Pass Generator (US-02)
* **User Story**: As a customer, I want to scan a receipt QR code so that I can add the coffee shop's loyalty card to my phone's native Wallet app without downloading a dedicated app.
* **Acceptance Criteria**:
  - GIVEN a mobile browser opens the QR landing page, WHEN the user clicks "Add to Wallet", THEN the server must compile a valid Apple PKPass file containing the shop's logo, colors, and a unique barcode.
  - GIVEN an Android device, WHEN the user installs the pass, THEN the system must render the pass correctly in Google Wallet.
* **Definition of Done**: Pass generated passes Apple SDK validation checks; scans successfully on physical scanners; renders customer name and dynamic barcode.

#### Feature 2: Barista Tablet Scanner App (US-01)
* **User Story**: As a barista, I want to scan a customer's wallet barcode using my tablet's front-facing camera so that I can reward points instantly.
* **Acceptance Criteria**:
  - GIVEN the scanner app is open, WHEN a customer pass is presented, THEN the camera must scan the Aztec/PDF417 barcode in under 1.5 seconds under standard cafe lighting conditions.
  - GIVEN a successful scan, WHEN the points update, THEN the screen must flash green and play a high-frequency success sound.
* **Definition of Done**: Local DB logs the scan; offline fallback stores scans in local storage; API latency is under 300ms.

#### Feature 3: Admin Settings Dashboard (US-03)
* **User Story**: As a shop owner, I want to set my loyalty rules (points per dollar, reward threshold) from a web dashboard.
* **Acceptance Criteria**:
  - GIVEN the admin dashboard settings page, WHEN I change the reward threshold to 8 points and save, THEN all future customers must require 8 points to trigger a reward.
  - GIVEN existing customer passes, WHEN settings are updated, THEN the system must push a background update to all active passes in Apple/Google servers.
* **Definition of Done**: DB schema updated; push notification sync script executes successfully; validation checks prevent saving negative point values.

---

### [3B] UNIT TEST CASES (Barista Tablet Scanner App)

| Test ID | Test Name | Preconditions | Steps | Expected Result | Type | Priority |
|---|---|---|---|---|---|---|
| **TC-001** | Happy Path Scan | Camera active; valid customer pass presented. | 1. Hold pass barcode in front of camera.<br>2. Wait for beep. | Pass scanned; points balance increments by 1; success tone plays. | Functional | P1 |
| **TC-002** | Offline Scanning | Tablet disconnected from Wi-Fi. | 1. Present valid pass barcode.<br>2. Confirm scan. | Scan saved in local queue; success tone plays; UI warns "Sync Pending". | Resilience | P1 |
| **TC-003** | Duplicate Scan Limit | Pass scanned 2 seconds ago. | 1. Present the same pass barcode immediately again. | UI displays "Scan Ignored: Duplicate check" warning; point balance unchanged. | Edge Case | P1 |
| **TC-004** | Invalid Barcode Type | Random barcode (e.g. UPC code on a box). | 1. Hold UPC code in front of camera. | Scanner rejects; displays "Invalid Pass Format"; plays error buzz. | Negative | P2 |
| **TC-005** | Low Light Scan | Ambient light < 50 lux. | 1. Present pass barcode in dark corner. | App automatically increases tablet screen brightness to assist scanning. | Usability | P2 |
| **TC-006** | Expired Pass | Pass marked inactive in database. | 1. Present inactive/disabled pass. | App alerts "Pass Expired/Disabled"; no points awarded. | Negative | P1 |
| **TC-007** | Concurrent Scans | Multi-tablet setups scanning same pass. | 1. Scan pass on Tablet A.<br>2. Scan same pass on Tablet B at same second. | DB registers only one scan; second scan returns validation error. | Concurrency | P2 |
| **TC-008** | Incomplete Data payload | Corrupt QR payload scan. | 1. Scan partially damaged/corrupt QR. | UI reports "Read Error: Please try scanning again." | Negative | P2 |
| **TC-009** | XSS Injection Check | QR payload containing Javascript payload. | 1. Scan a QR pass carrying a code injection payload. | Payload treated as plain text string; input sanitized; system remains secure. | Security | P1 |
| **TC-010** | Unauthorized Tablet | De-registered tablet device. | 1. Attempt scan on tablet whose token was revoked. | API rejects request with 401 Unauthorized; local interface locks down. | Security | P1 |

---

### [3C] SPRINT PLAN (Sprint 1)

* **Sprint Goal**: *"Enable a barista to scan a digital wallet pass and successfully update point balances on a mobile device."*
* **Estimated Velocity**: 24 Story Points.
* **Team Capacity**: 3 Developers (1 Frontend, 1 Backend, 1 Full-Stack) + 1 Product Manager/Scrum Master.
* **Commitment Backlog**:
  - `US-01`: Barista Tablet Scanner UI & Camera Logic (8 points)
  - `US-02`: Apple Wallet Pass compilation API (8 points)
  - `US-03`: Basic merchant settings schema and update page (5 points)
  - `SPIKE`: Offline data storage research on Android (3 points)
* **Risk Mitigation (Days 1-3)**: The Apple `.pkpass` compilation certificate registration is our highest risk. The backend engineer must complete this setup on Day 1 to ensure developers have mock passes for testing.
* **Definition of Sprint Success**: A working tablet app mockup scans a newly generated wallet pass, updating the backend database with zero errors.

---

# PHASE 4 — SHIP

### [4A] GO-TO-MARKET (GTM) PLAN

#### 1. Launch Goals (30/60/90 Days)
- **30 Days**: 10 coffee shops live in the local metro area; 500 active customer passes installed.
- **60 Days**: 30 coffee shops live; >2,000 active customer passes.
- **90 Days**: Monthly recurring revenue (MRR) of $1,200; less than 5% monthly merchant churn.

#### 2. Target Wedge Segment
- Independent, single-location coffee shops located in student-dense urban districts. These shops have tech-savvy clienteles and are highly motivated to offer digital programs to compete with national chains.

#### 3. Messaging Framework
- **Headline**: *Starbucks-grade loyalty passes, built for independent coffee shops.*
- **Sub-headline**: *Give your customers digital wallet loyalty passes in seconds. No apps to download, no hardware to replace. Start driving repeat visits on autopilot.*
- **Key Benefits**:
  - *Boost Visits*: Automate SMS reminders to bring back lapsed regulars.
  - *Zero App Friction*: Pass downloads instantly into Apple & Google Wallet.
  - *Simple Setup*: Runs on any standard tablet at your counter.

#### 4. Channel Strategy
1. **Direct Outbound (Foot Campaign)**: PM and sales lead walk into target cafes during slow afternoon hours (2-4 PM) to demo the app directly to owners.
2. **Local Cafe Owners Facebook/Reddit Groups**: Share case studies of early pilot metrics.
3. **Barista Referral Network**: Offer a $50 gift card to any local barista who introduces us to their shop owner.

#### 5. Pre-Launch Readiness Checklist
- [x] Apple Developer Enterprise account certificates active.
- [x] Twilio API production account set up with SMS compliance registry.
- [x] Printed merchant starter kits (QR code acrylic stands) ready for distribution.
- [x] Terms of service and privacy policy uploaded.
- [x] Staging/UAT environment tests completed.
- [x] Customer support hotline and email ticket system live.
- [x] Security audit on point validation API completed.
- [x] Telemetry dashboards in Amplitude verified.

#### 6. Launch Day Playbook (Day 1)
* **07:00 AM**: Confirm server status; monitor real-time API logs.
- **08:00 AM**: On-site support at our first 3 pilot shops during morning rush.
- **12:00 PM**: Send launch announcement newsletter to local business registries.
- **03:00 PM**: Run social media launch announcement campaigns.
- **06:00 PM**: Conduct post-rush debrief with pilot shop baristas to gather UI feedback.
- **09:00 PM**: Review day 1 telemetry metrics (total scans, installs, error logs).

#### 7. Kill Criteria
- System crash rates exceed 1% of total API calls.
- Customer pass validation latency exceeds 5 seconds.

---

### [4B] A/B TEST PLAN

#### Test 1: Sign-Up Flow Opt-in Friction
* **Hypothesis**: *We believe that asking for only the customer's phone number during pass download will result in a 25% increase in completed sign-ups compared to asking for phone number AND email, because reducing input fields decreases cognitive friction.*
* **Control (A)**: Inputs required: Name, Phone, and Email.
* **Variant (B)**: Inputs required: Phone number only (with optional name field).
* **Primary Metric**: Wallet installation conversion rate.
* **Guardrail Metric**: Opt-out rate of SMS alerts (checks if lack of email leads to higher SMS churn).
* **Sample Size**: 800 visitors per variant.

#### Test 2: In-Store Call-to-Action Messaging
* **Hypothesis**: *We believe that a QR stand offering a concrete reward ("Scan to start earning your free coffee") will drive higher conversion than a generic brand message ("Join our digital loyalty club") because it highlights immediate time-to-value.*
* **Control (A)**: "Join our digital loyalty club! Scan here."
* **Variant (B)**: "Get a free espresso on your next visit! Scan to join."
* **Primary Metric**: QR Code scan-to-visit CTR.
* **Guardrail**: Reward cost margins (makes sure offering free items doesn't drain shop margins).
* **Sample Size**: 1,200 store visits per variant.

---

### [4C] STAKEHOLDER UPDATE (Launch Week)

> **TL;DR**: BeanFlow CRM is live in 5 pilot shops; initial customer adoption metrics are exceeding targets by 15%.
> 
> **RAG Status**: **GREEN**
> - Setup and deployments completed on time. System latency is healthy at 180ms.
> 
> **Key Progress This Week**:
> - Completed production deployments for Merchant App and Apple Wallet API.
> - Onboarded 5 local pilot cafes in the university district.
> - Recorded 142 unique wallet pass installs and 89 loyalty point transactions.
> 
> **Risks on Radar**:
> - *Twilio SMS delivery latency*: SMS verification codes delayed on certain carriers.
>   - *Owner*: Backend Engineer. *Mitigation*: Enable carrier fallback routing; ETA: Friday.
> 
> **Ask from Leadership**:
> - Approvals for an additional $500 monthly budget allocation for Twilio SMS messaging.
> 
> **Next Milestone**:
> - Phase 2 rollout targeting 15 additional merchants by June 28th.

---

### [4D] PRICING STRATEGY

#### 1. Recommended Model
* **Hybrid Freemium/SaaS**: Free up to 100 customer passes per shop. Above 100 passes, the shop pays a flat monthly fee based on locations.
* *Why?* Removes all risk for owners during onboarding, allowing them to validate the product's effectiveness before paying.

#### 2. Tier Structure
* **Hobbyist (Free)**: 1 location, up to 100 active members, basic digital stamp card.
* **Growth ($29/month)**: 1 location, unlimited members, automated SMS re-engagement campaigns, basic dashboard.
* **Pro ($59/month)**: Up to 3 locations, custom branding, API integrations, daily CSV data exports.

#### 3. Value Metric
* **Number of Active Locations**: Small business owners think of their costs in terms of store locations, making this the most intuitive axis to charge on.

#### 4. Anchoring Strategy
The **Growth Tier ($29/mo)** is highlighted in green on the pricing page with the label "Best Value for Local Cafes," anchored against the $59/mo Pro tier and the much higher costs of competitor POS loyalty systems ($45-$50/month).

---

# PHASE 5 — LEARN

### [5A] CHURN & RETENTION DIAGNOSIS

#### 1. Churn Diagnosis (Top 3 Root Causes)
- **Barista Friction**: Baristas stop asking customers to scan because the scanning process takes too long or bugs out, causing the customer to abandon the pass.
- **No Value Realization**: Customers download the pass but forget they have it because the shop rarely updates its loyalty offers or sends updates.
- **In-App Navigation Issues**: Merchants find the dashboard UI confusing and stop checking their stats.

#### 2. The "Aha!" Moment Audit
- A customer reaches their "Aha!" moment when they **accrue their 3rd loyalty point within 10 days of pass installation**. At this stage, visiting the shop has become a habit, and retention rates increase by 45%.

#### 3. 5 Retention Experiments
1. **Push Notifications on Lockscreen**: Display point updates and reminders directly on the phone's lock screen when the user walks near the shop (geofencing).
2. **Barista Incentive Leaderboard**: Show a weekly tally of scans per barista in the merchant app, awarding a coffee bag to the top performer to encourage scan promotion.
3. **Day 3 Check-in SMS**: Automatically text a customer on Day 3 if they haven't visited, saying: *"Your favorite brew misses you. Stop by this week for 10% off."*
4. **Instant Double Points Promo**: Award double points on the customer's second visit to accelerate them to their 3rd point habit threshold.
5. **Interactive Quick-Scan Widget**: Build a tablet home-screen widget to let baristas launch the scanner with a single tap.

#### 4. Lifecycle Message Strategy
- **Day 1**: Welcome SMS: *"Thanks for joining BeanFlow! Show your card at check out to get closer to your free cup."*
- **Day 3**: Educational SMS highlighting that the card is safely stored in their phone's native Apple/Google Wallet.
- **Day 7**: Progress reminder: *"You're only 3 points away from your free espresso! See you tomorrow?"*
- **Day 14**: Re-engagement offer: *"We haven't seen you in a week! Show this text to your barista for a free pastry upgrade with your coffee."*
- **Day 30**: Monthly impact digest sent to owners, showing them how much extra revenue BeanFlow generated for their shop.

---

### [5B] TRADE-OFF DECISION

#### Context
At Day 45 post-launch, engineering reports a resource constraint: we can either fix a critical local DB sync bug that causes offline tablet scans to delay, or build the scheduled automated SMS campaign feature.

#### Options Analysis
* **Option A: Fix Local DB Sync Bug**:
  - *Gains*: Clean database metrics; eliminates barista frustration; protects core usability during peak rush hours.
  - *Losses*: Delays the marketing features needed to prove customer retention loops.
  - *Reversibility*: High. *Risk*: Low.
* **Option B: Build SMS Marketing Feature**:
  - *Gains*: Provides owners with the re-engagement tool they have been requesting.
  - *Losses*: Unsynchronized scans will continue to delay, causing customer disputes over point balances.
  - *Reversibility*: Medium. *Risk*: High (bugs at the checkout counter will kill store manager trust).

#### Recommendation
**Fix the local DB sync bug first (Option A)**. 
*Rationale*: A loyalty system's success relies on trust at the cash register. If a customer's point balance is wrong or delays because of a sync bug, it creates transaction friction. In F&B, speed and accuracy at checkout are critical. We must ensure our foundation is stable before layering on marketing features.

#### Decision Memo (To: CEO)
> **Subject: Prioritizing checkout reliability over SMS marketing features**
> 
> We have decided to delay the release of our automated SMS marketing module by 1 sprint to prioritize fixing a local DB synchronization issue affecting our merchant scanner. Over the last 7 days, we recorded 12 checkout delays due to unsynced local transaction records. If a customer's points fail to update instantly during the morning rush, checkout lines slow down, and we risk losing store manager trust. We will dedicate this sprint to making the scanner system robust, resuming work on the SMS marketing features in the following sprint.

---

### [5C] 6-MONTH ROADMAP

#### Phase 1 (Months 1-2): Foundation
- Features: Core Wallet Pass compiler, Merchant Android/iOS Scanner app, settings portal.
- Success Metric: **WAL** > 500; transaction latency under 2 seconds.
- Risk: Delayed Apple Developer account approvals. *Mitigation*: Run early pilots using Google Wallet and web passes.

#### Phase 2 (Months 3-4): Engagement & Growth
- Features: Dynamic QR codes (anti-fraud), automated SMS check-ins, barista incentives.
- Success Metric: Wallet pass install rate > 25%.
- Risk: Twilio SMS pricing limits. *Mitigation*: Add email fallbacks.

#### Phase 3 (Months 5-6): Retention & Monetization
- Features: Multi-location merchant accounts, premium pricing tier gating, Stripe integrations.
- Success Metric: $2,000 MRR; merchant churn < 3%.
- Risk: Incumbents (Square) lowering add-on pricing. *Mitigation*: Focus on our standalone, payment-processor-agnostic value proposition.

* **North Star Metric (Month 6 Target)**: **WAL** > 5,000.
* **What Gets Cut If Behind**: Multi-location merchant accounts (we will focus exclusively on single-location boutiques).

---

### [5D] POST-MORTEM (Double-Reward Exploit)

#### Executive Summary
On June 10th, an exploit was discovered where customers could receive double points by scanning their pass barcode simultaneously on two tablets at the same register. This affected 4 pilot shops and led to 32 illegitimate free coffee redemptions before the exploit was patched. The issue was resolved by implementing a centralized transaction locking database.

#### Root Cause (5 Whys)
1. *Why did customers get double points?* They scanned their passes on two separate tablets at the same time.
2. *Why did the tablets accept both scans?* Each tablet processed the transaction locally before syncing with the database.
3. *Why did they process locally without verifying?* To support offline operations, the scanner app updates the local cache before running the server API call.
4. *Why did the server accept both synced transactions?* The server lacked a validation check to block transactions with identical timestamps.
5. *Why was this validation check missing?* The team prioritized development speed for the offline sync feature, omitting timestamp checks.

#### Contributing Factors
- Lack of QA concurrency tests during staging.
- Shop layouts placing two registers closer together than expected.

#### What Went Well
- The engineering team detected the anomaly and deployed a database lock hotfix within 4 hours of the first support ticket.

#### Action Items

| Action Item | Target Date | Owner |
|---|---|---|
| Implement centralized redis lock on point-accrual API. | Completed | Lead Backend |
| Add a 60-second cooldown window to same-user scan API calls. | June 15 | Frontend Dev |
| Build automated concurrency tests into our CI/CD pipeline. | June 20 | QA Engineer |
| Reimburse affected merchants for the cost of the exploited coffee. | June 14 | Product Manager |

#### Process Change
We now require all feature specs that modify account balances (points, rewards, cash) to undergo a mandatory concurrency architecture review before engineering begins.

#### Customer Communication Template
> **Subject: Security Patch Deployment and System Update**
> 
> We recently identified a software error that affected point balance sync times in your shop yesterday. Our team has deployed a security update to resolve this issue and prevent any duplicate transactions. We have corrected the affected customer logs. As part of our commitment to your business, BeanFlow will reimburse your shop for the cost of any excess rewards claimed during this period. Thank you for your patience as we build a more secure system for your business.

---

## FINAL DELIVERABLE — THE ONE-PAGE BRIEF

* **The Problem**: Independent coffee shops lack affordable, digital tools to track customer retention, forcing them to rely on fragile paper punch cards that capture no user data.
* **The Solution**: BeanFlow CRM — a digital stamp card that installs directly into native Apple/Google Wallets via QR scan, paired with automated SMS marketing tools for the shop owner.
* **The User**: Boutique, independent coffee shop owners, store managers, and their checkout baristas.
* **The Market Gap**: A simple, loyalty pass system that runs standalone on any tablet next to the register, without requiring deep integrations into complex POS hardware.
* **North Star Metric**: **Weekly Active Loyals (WAL)**. *Target*: 5,000 active customer scans by Month 6.
* **Top 3 Features**:
  1. *Scan-to-Wallet Pass compiler*: Renders passes directly into Apple/Google Wallet.
  2. *One-tap Barista Scanner*: An ultra-fast scanner app for merchant tablets.
  3. *Automated SMS engine*: Sends re-engagement texts to inactive regulars.
* **6-Month Roadmap Summary**:
  - *Month 1-2*: Launch MVP tablet scanner and Wallet pass generator.
  - *Month 3-4*: Roll out dynamic QR codes and automated SMS campaigns.
  - *Month 5-6*: Introduce multi-location support and premium pricing tiers.
* **Biggest Risk & Mitigation**: Barista scanning fatigue causing checkout delays. We mitigate this by keeping the scan interface simple, and testing camera scan speeds weekly to keep latency under 1.5 seconds.
* **Success at Month 6**: 50 active merchants onboarded, 5,000+ active customers using the system, and less than 3% monthly merchant churn.
