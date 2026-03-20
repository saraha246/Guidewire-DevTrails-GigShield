# Guidewire-DevTrails-GigShield
AI-powered parametric income insurance for delivery partners; instant payouts for weather and disruption-based income loss.

**GigShield – AI-Powered Parametric Income Insurance for Food Delivery Partners**

# The Problem

India is home to food delivery partners (Zomato, Swiggy) who form the backbone of our food landscape. But when external shocks hit our cities, such as rain, heat, floods, or imposition of curfews, their income is zero. They have no safety nets. They have no insurance. They have no backup.

**GigShield** is a solution that provides automated and parametric income insurance.

**Persona: Food Delivery Partner (Zomato / Swiggy)**

*Meet Ravi, 26, Chennai*
- Delivers for 6-8 hours a day on his two-wheeler
- Earning ₹600 - ₹900/day depending on orders
- Works for 6 days a week → ₹3,500 - ₹4,500/week
- No support when Chennai is flooded, heatwaves occur, and sudden curfews are implemented
- Cannot afford high insurance premiums

**Ravi's Disruption Scenarios:**

| Scenario                      | Disruption                                     | Income Impact          |
|------------------------------ |----------------------------------------------  |----------------------- |
| Heavy monsoon rain (>50mm/hr) | Cannot ride safely, platform pauses deliveries | 100% daily income lost |
| Extreme heat (>42°C)          | Platform reduces delivery slots, heat advisory | 50-70% income lost     |
| Flash flood / waterlogging    | Roads blocked, deliveries halted               | 100% daily income lost |
| Sudden local curfew / bandh   | Unable to access pickup/drop zones             | 100% daily income lost |
| Severe AQI pollution (>300)   | Health advisory, reduced outdoor activity      | 40-60% income lost     |

# Our Solution: GigShield

GigShield is a "Web-based AI-powered parametric insurance platform" that includes the following features:

1. Onboarding of delivery partners in less than 2 minutes
2. Profiling of risks for each delivery partner using AI/ML algorithms considering location, work history, and disruptions in the area
3. Selling of weekly policies to these delivery partners in a dynamic pricing manner considering their profiled risk scores
4. Monitoring disruptions in real-time using weather and civic APIs
5. Triggering of claims automatically without any manual intervention required
6. Paymenting out instantly to UPI/wallet upon breach of a threshold condition
7. Detection of fraudulent claims using anomaly detection and GPS validation

> We only insure "lost income" and nothing else. No health, no vehicle, no accidents.

# Platform Choice: Web Application

We have chosen a "Responsive Web Application" instead of a Mobile Application for the following reasons:

- Faster development and deployment in a 6-week timeframe
- No waiting for app approval from the app stores
- Easier for judges and evaluators to access directly via a browser link provided to them
- Much richer analytics possible for a web application compared to a mobile app
- Mobile responsiveness is possible on a web application, so it can be accessed from any smartphone browser.

# Scaling Beyond Chennai
GigShield rolls out in Chennai as a planned launch in a city that we've deliberately selected for its extreme and well-known disruption patterns, including annual monsoon floods, cyclones, and extreme heatwaves. Every aspect of our stack, from SENTINEL's fraud detection capabilities to our reinsurance layer, is designed to be city-agnostic from day one. Expanding into Mumbai, Bengaluru, Delhi, or Hyderabad requires nothing more than adjusting our zone risk score and seasonal factors based on that city's unique disruption patterns. In fact, our parametric trigger model, which currently includes weather-related events, can easily expand to include city-specific disruption events such as Mumbai's local train strikes, Delhi's pollution-related shutdowns, or Bengaluru's tech park traffic curfews, making each of these metropolises a potential GigShield market in India.

# Financial Model & Weekly Premium Structure

# Why Weekly?
Since our target segment is "delivery partners," they are paid on a weekly basis by these apps. Their earnings are not predictable on a daily basis. A weekly premium is directly aligned with their cash flows. A monthly premium poses affordability issues for them. A daily premium poses administrative issues. Only a weekly premium makes sense for them.

# The Financial Foundation: Loss Ratio
Every choice in our financial model is centered on a single number:

**Loss Ratio** = Total Claims Paid ÷ Total Premiums Collected


| Loss Ratio     | What It Means                                             |
|------------    |-------------------------------------------------------    |
| Less than 40%  | Overcharging workers - unsustainable brand and high churn |
| 60-70%         | Industry standard - healthy and sustainable               |
| More than 100% | Paying out more than we take in - bankruptcy              |

**GigShield's goal is a 65% loss ratio across all tiers**.

Every premium, every payout, and every threshold is designed around this number.


# Payout Structure: Proportional Income Replacement

GigShield does not use flat payouts. Flat payouts cause two major issues: they overpay those who make less and underpay those who make more.

Our payouts are instead calculated as a **percentage of the worker's average daily earnings**, times the number of hours they were disrupted:

**Payout** = (Verified Average Daily Earnings / 8 hours) × Disruption Hours × Coverage Rate

**Coverage Rates by Tier:**

| Tier                    | Coverage Rate      | Why                                  |
|------                   |--------------      |-----                                 |
| Basic Shield            | 50% of lost income | Entry-level, lower premium           |
| Standard Shield         | 65% of lost income | Industry standard replacement rate   |
| Pro Shield              | 75% of lost income | Max protection for full-time workers |

**Why not 100% replacement?**
Replacing 100% of income eliminates the need to go back to work as soon as possible. The industry standard is 60-70%. We use this range for our coverage because it strikes a balance between providing adequate protection and managing moral hazard.

**Worked Example — Ravi during a 4-hour flood disruption:**
- Average daily earnings of Ravi: ₹750/day
- Average hourly earnings of Ravi: ₹750/day / 8 hrs/day = ₹93.75/hr
- Number of disrupted hours: 4 hrs
- Coverage rate: 65%
- *Payout Calculation: ₹93.75/hr * 4 hrs * 0.65 = ₹243.75*

Honest, fair, and financially sustainable.


# Weekly Premium Structure

Our base premium is designed so that we achieve a 65% loss ratio at expected claim frequency:

| Tier            | Weekly Premium | Coverage Rate          | Best For                 | Expected Annual Premium |
|------           |--------------- |--------------          |----------                |------------------------ |
| Basic Shield    | ₹39/week       | 50% income replacement | Part-time (< 20hrs/week) | ₹2,028/year             |
| Standard Shield | ₹65/week       | 65% income replacement | Regular (20-40hrs/week)  | ₹3,380/year             |
| Pro Shield      | ₹99/week       | 75% income replacement | Full-time (40hrs+/week)  | ₹5,148/year             |
 
**Why these premiums work:**
- Chennai receives 8-12 significant disruption events per monsoon season (June - September)
- Average duration per disruption: 3-5 hours
- At a loss ratio of 65%, Standard Shield at 65/week pays out expected seasonal payouts with an operational margin

# AI-Driven Dynamic Pricing

The premium for the week is *not static*. Using our ML model, we update it based on four factors:

**Factor 1: Zone Risk Score**
Disruption frequency per zone based on historical disruption events. Velachery has a higher multiplier than Nungambakkam due to flood vs. elevated terrain risk.

**Factor 2: Seasonal Risk Factor**

| Season              | Month             | Factor |
|--------             |-------            |--------|
| Monsoon (high risk) | June–September    | 1.35×  |
| Post-monsoon        | October–November  | 1.15×  |
| Summer heatwave     | April–May         | 1.20×  |
| Low risk            | December–March    | 1.00×  |

**Factor 3: Worker Activity Score**
The more active workers we have, the higher income at risk for them. More active workers mean slightly higher premium for them, which is fair and proportionate.

**Factor 4: SENTINEL Loyalty Discount**
Workers with clean claim history and high Corroborator Credit scores qualify for up to 10% premium discount.

**Final Premium Formula:**

Final Premium = Base Premium × Zone Risk Score × Seasonal Factor × SENTINEL Loyalty Discount


**Example — Ravi in July, Velachery:**

₹65 × 1.3 (zone) × 1.35 (monsoon) × 0.95 (clean history) = ₹108.25/week

Ravi pays ₹108/week during peak monsoon for 65% income replacement. That's ₹15.43/day — less than a cup of chai — for meaningful financial protection.

# Catastrophic Event Management: Reinsurance Layer

**The single biggest financial risk in parametric insurance: the entire city floods at once.**

If a Category Red weather hits Chennai, all workers in all zones file claims at the same time. No startup insurer survives this scenario without a plan.

GigShield solves this via a two-tier liability structure:      

**Factor 2: Seasonal Risk Factor**

| Season              | Month            | Factor |
|--------             |-------           |--------|
| Monsoon (high risk) | June–September   | 1.35×  |
| Post-monsoon        | October–November | 1.15×  |
| Summer heatwave     | April–May        | 1.20×  |
| Low risk            | December–March   | 1.00×  |

**Factor 3: Worker Activity Score**
The more active workers, the more income is at risk for them. The more active workers, the slightly higher premium for them. This is fair and proportionate.

**Factor 4: SENTINEL Loyalty Discount**
Workers with clean histories and high Corroborator Credit scores qualify for up to 10% premium discounts.

**Final Premium Formula:**

Final Premium = Base Premium × Zone Risk Score × Seasonal Factor × SENTINEL Loyalty Discount

**Example: Ravi’s Premium for July, Velachery**

₹65 × 1.3 (Zone) × 1.35 (Monsoon) × 0.95 (Clean History) = ₹108.25/week

Ravi’s premium is ₹108/week. This is for 65% income replacement. This is ₹15.43/day. This is for a cup of chai. This is for significant financial protection.

# Catastrophic Event Management: Reinsurance Layer

**The single biggest financial risk for a parametric insurance startup: The entire city floods at once.**

If a Category Red weather hits Chennai, all workers from all zones will file claims at once. No startup insurer will survive such a scenario.
GigShield achieves this by providing a *two-tier liability structure*:

Tier 1: Normal Operations (GigShield absorbs)
- Claims volume is within 2x of the expected average weekly claims
- Funded from the premium pool
- Target loss ratio: 65%

Tier 2: Catastrophic Event (Reinsurance Partner absorbs)
- Triggered when claims exceed 3x normal weekly volume within 24 hours
- Excess liability is passed to the reinsurance partner
- GigShield pays the reinsurance premium from operational margin
- Employees receive the same payouts; reinsurance is not visible to them
This is standard industry practice. In the context of the hackathon, this would be modelled as a partnership with a simulated reinsurance entity, with the premium being 8% of total premiums collected and set aside for reinsurance costs.


# Unit Economics & Path to Profitability

Per Worker Per Week (Standard Shield, normal season):

| Item                             | Amount          |
|------                            |--------         |
| Premium collected                | ₹65.00          |
| Expected claim payout (65% LR)   | ₹42.25          |
| Reinsurance reserve (8%)         | ₹5.20           |
| Operation cost per user          | ₹8.00           |
| *Net margin per worker per week* | *₹9.55 (14.7%)* |

Break-even analysis:
- Fixed monthly operational costs (hosting, APIs, staff) ~₹50,000/month
- Break-even at: ~1,200 active Standard Shield subscribers
- Target: 5,000 active subscribers in Chennai → *₹47,750/week net margin*

SENTINEL's direct financial impact:
For every fraudulent claim that SENTINEL prevents, our direct impact on loss ratio. If SENTINEL can prevent 15% of fraudulent claims, LR decreases from 65% to ~55%. This translates to a direct increase in net margin of ~₹6.50 per worker per week. This translates to *₹32,500/week at 5,000 subscribers solely from fraud reduction.*

**AI/ML Integration Plan**

1. DPC : Dynamic Premium Calculation
- Model: Gradient Boosting Regressor (scikit-learn)
- Attributes: Zone risk rating, seasonality, worker activity, claims history, local disruption rate.
- Output: Individualised weekly premium per employee.

2. Fraud Detection
- Model: Isolation Forest + Rule-based checks.
- Checks:
  - GPS position when the trigger took place (was the worker in the affected area?)
  - Activity data (has worker been logged into delivery app?)
  - Duplicate claim identification (same worker, same event, same policy)
  - Scoring of historical anomalies (abnormal claim patterns)

3. Predictive Risk Modelling
- Model: Time-series forecasting (Prophet / LSTM)
- Output: Activity disruption probability per area for the following week, for proactive premium adjustment and worker alerts.

# Tech Stack

Frontend: React.js with Tailwind CSS for a responsive, mobile-friendly web interface and worker dashboard
Backend: Python with FastAPI to handle REST APIs, business logic, and real-time processing
Database: PostgreSQL for storing worker profiles, policies, and claims data
Machine Learning: scikit-learn and pandas for dynamic premium calculation and fraud detection
Weather Data: OpenWeatherMap (free tier) for real-time disruption triggers
Air Quality: OpenAQ API for AQI-based triggers
Civic Alerts: Mock API to simulate curfews and disruption scenarios
Payments: Razorpay (Simulation Mode) for demonstrating instant payouts
Hosting: Vercel (frontend) and Render (backend) using free-tier deployment
Version Control: GitHub for repository management and collaboration


# Application Workflow

Worker Onboarding (2 min)
    |
AI Risk Profiling (zone + history + activity)
    |
Weekly Policy Choice + Dynamic Premium Displayed
    |
Payment (Razorpay test mode)
    |
Policy Active — Real-time disruption monitoring starts
    |
Disruption identified (API threshold crossed)
    |
Fraud validation (GPS + activity check)
    |
Auto approval and UPI payout activated
    |
Worker notification + Dashboard updated

# Development Plan

Phase 1: Ideation and Foundation
-Define persona and disruption cases
-Weekly premium model design
-Parametric triggers
-Plan tech stack
-Set up GitHub repository
-Establish project infrastructure
-Create wireframes

Phase 2: Automation and Protection
-Worker registration and onboarding flow
-Dynamic premium calculation using AI
-Policy creation and management
-Automated parametric triggers (weather/AQI/civic APIs)
-Zero-touch claims management
-Razorpay test mode integration
-Rule-based basic fraud detection

Phase 3: Scale and Optimise
-Sophisticated ML fraud detection (Isolation Forest + GPS authentication)
-Predictive risk modelling (next-week disruption forecasting)
-Worker dashboard (earnings protected, live insurance status)
-Admin/insurer dashboard (loss ratios, predictive analytics)
-Instant payout simulation
-Final pitch deck
-5-minute demo video

# Adversarial Defense & Anti-Spoofing Strategy

Critical Update — Phase 1 Compliance: SENTINEL, the four-layer anti-syndicate architecture introduced by GigShield in response to the coordinated GPS-spoofing syndicate threat, does not try to identify fraud after it occurs. It anticipates it, maps it socially, validates it with ground-level data, and continues to protect all honest workers in the process.

"We don't verify claims. We verify reality."

**The Core Insight**

All other platforms cross-reference GPS with cell towers. Syndicates know this and adapt. GigShield's defense against GPS spoofing is built on one fact that GPS spoofing cannot replicate:

**Genuine distress does not produce the same human behaviour as coordinated fraud.**

An honest delivery partner caught in a flood does not open their insurance app. They call their family, try to move their bike, text their delivery service. The fraudster sits at home waiting for the Telegram signal — and opens the app the moment it comes.

SENTINEL is built on observing this distinction across four layers.

**Layer 1: PRE-CRIME ENGINE — Predicting Syndicates Before They Strike**

The problem with all current fraud detection: it is reactive. It waits for claims to come in. GigShield acts before the claim is ever filed.

How it works:
- The Weather API monitors disruption areas.
- When rainfall approaches 40mm (our payout threshold), SENTINEL activates Pre-Crime Watch Mode in that area.
- The system tracks suspicious app behaviour within that zone:
  - Sudden app opens (more than 3x the normal rate)
  - Mass policy-check requests within 5 minutes
  - Workers inactive for days suddenly bursting in with logins

The point: real workers don't check their insurance app when rain starts. They're trying to finish their last delivery or find shelter. Fraudsters do — because they're on Telegram waiting for the signal.

Once Pre-Crime Watch Mode detects a suspicious spike, all subsequent claims in that area for the next 60 minutes are automatically placed in elevated scrutiny mode before a single rupee is disbursed.

Weather exceeds 40mm threshold
          |
SENTINEL switches to Pre-Crime Watch
          |
Monitors app opens, login rate, and policy checks
          |
Spike detected? — Elevated Scrutiny mode activated
No spike? — Normal claims processing continues

**SOCIAL GRAPH ANALYSIS: Layer 2 Mapping the Ring.**

GPS spoofing conceals your whereabouts. It cannot hide who you know.

The members of the syndicates do not come out of thin air. They directed one another to GigShield. They joined within days of one another. Their areas of delivery are exactly the same. Their claim times are related not only in this incident - but also in several previous incidents.

How it works:
GigShield constructs a Worker Social Graph out of:
- So-called referral chains (invited by whom)
- Onboarding time clustering (did 50 workers go on within 48 hours of one another?)
- Time zone overlap of historical areas (do they always work the same streets?)
- Cross-event claim correlation (with this same cluster file together within the previous three triggers)?

In case of a mass claim event SENTINEL executes a Ring Score on the cluster:

| Signal                               | Weight     |
|--------                              |--------    |
| Referred each other                  | High |
| Onboarded same week                  | Medium |
| Claim across events always           | Very High |
| Zone overlap >80%                    | Medium |
| Neither claimed singly nor in groups | High |

High Ring Score does not block assertions at all — the cluster is classified as corroborated in Layer 3. True mass strandings have an impact on strangers. Friend groups are influenced by fraud rings.

**CORROBORATION NETWORK: Layer 3 Ground Truth. The crowdsourced ground truth.**

This is where against which no syndicate can organize.

On filing a claim, SENTINEL pings 3 to 5 other registered GigShield workers who happen to be in the same zone by randomly and silently sending them a single push notification:

**"Quick check? — can we deliver there now? Tap Yes or No."**

When workers are pinged they are not aware that they are giving credence to another person. They believe it to be a regular platform examination. This can never be coordinated in Telegram since:
- Employees do not receive information on when they are to be pinged.
- Employees do not understand to whom they are lending credence.
- Ping will be sent to randomly chosen workers, but not to the own members of the syndicate.

Corroboration outcome:
- Majority answer YES — Claim trust score increased, quickened payouts.
- Majority No — Flagged, under human inspection.
- No reply (poor network) — No reply, proceeds as usual.

Those workers who make a response to corroboration ping regularly and consistently over time will receive Corroborator Credits — minor loyalty rewards that encourage them to play in the network truthfully.

This is based on the approach of the Indian microfinance, namely, community accountability as a financial instrument of the Self-Help Groups (SHGs).

**Layer 4: HONEST WORKER GUARANTEE. The UX Safety Net.**

The greatest danger of aggressive detection of fraud is punishing the people who are innocent.

A real delivery partner who is stuck in the middle of a Chennai flood with low network connection cannot be considered a criminal. GigShield publicly makes the following commitment that no other platform makes:

In case your valid claim has been held up beyond 2 hours on account of a screening of fraud, you are reimbursed 50 goodwill credit. No questions asked. No application needed.

This is not just a UX feature. It is a strategic assertion: we are so sure about our fraud-detecting, we are ready to pay our own false-positive.

3-Tier Claim Resolution:

Tier 1 — Auto Approved (SENTINEL Score 0.75 and above)
- Instantaneous release of Payout to UPI.
- 0 friction, 0 questions.
- Worker receives: "Claim approved. X on the way."

Tier 2 — Soft Flag (SENTINEL Score 0.45–0.74)
- Worker gets: "We are confirming your coverage because there are network conditions in your location. Usually resolves in 30 minutes."
- System passively re-checks through cell tower + corroboration network.
- Passes — instant payout.
- Fails — Tier 3.
- Employee never informed that he has been suspected of fraud.

Tier 3 — Human Review (SENTINEL Score < 0.45)
- Employee gets: "We require one fast thing to approve your claim, may we know when and where you are? Can you please provide your present position picture or your delivery app screenshot?"
- It is put in the form of a network problem, never a charge.
- Resolved within 2 hours.
- Approved — payout + 50 goodwill credit automatic.
- Rejected — appeal within 7 days with a clear explanation.


SENTINEL Full Architecture


                 WEATHER CROSSES 40mm
                          |
             +--- LAYER 1: PRE-CRIME ENGINE ---+
             |   Monitor app behaviour          |
             |   Login spike detected?          |
             +---------------+-----------------+
                             |
                       CLAIM FILED
                             |
             +--- LAYER 2: SOCIAL GRAPH -------+
             |   Ring Score calculated          |
             |   Are claimants connected?       |
             +---------------+-----------------+
                             |
             +--- LAYER 3: CORROBORATION ------+
             |   Silent peer ping sent          |
             |   Ground truth returned          |
             +---------------+-----------------+
                             |
                    SENTINEL SCORE (0-1)
                             |
          +------------------+------------------+
          |                  |                  |
     Score >= 0.75    Score 0.45-0.74      Score < 0.45
     Auto Approve      Soft Flag           Human Review
     Instant payment   Re-check            Evidence Requirement
          |                  |                  |
                   LAYER 4: HONEST WORKER GUARANTEE
                   (50 credit if delayed > 2 hours)


It is impossible to beat SENTINEL because it is very fast and a very fine pilot.

Counter to the Attack Vector of SENTINEL:

| Attack Vector                                     | SENTINEL Counter                                                          |
|--------------                                     |------------------                                                         |
| Pre-Crime Engine app behaviour spike before claim | Pre-Crime Engine catches application behaviour spikes |
| Coordinated Telegram filing                       | Social Graph identifies the ring across several past events |
| Fake location during trigger                      | Corroboration Network acquires ground truth among disengaged workers |
| Multi-signal score                                | Requires consistent legitimate behaviour in all 4 layers |
| Hacker spoofing methods                           | Pre-Crime Engine is signature-free, not behavioural — evolves autonomously |



# What We Explicitly Exclude

According to competition regulations, GigShield does not include:
- Health or medical expenses
- Accident or injury claims
- Vehicle repair or damage
- Any personal liability

# Team
Frontend + UI/UX
Backend + APIs
ML/AI + Data
DevOps + Integration

Links
- Demo Video: [Link to 2-min video]


GigShield — Since each delivery is to be covered by a safety net.
