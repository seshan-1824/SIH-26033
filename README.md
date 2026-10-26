# Smart India Hackathon Workshop
# Date:18/10/2026
## Reference Number:26011453
## Name:Seshan.B

## Problem Title
SIH 26033: Multiple intermediaries reduce farmers earnings and increase consumer prices.

## Problem Creater's Organization
Ministry of Consumer Affairs, Food & Public Distribution

## Theme
Agriculture, FoodTech & Rural Development

## Problem Description
Expected Solution: Create a digital marketplace that:

• Connects farmers/FPOs directly with consumers and bulk buyers.
• Provides logistics support.
• Uses AI for demand forecasting and route optimization.

Benefits:

• Better prices for farmers.
• Lower prices for consumers.
• Reduced supply chain inefficiencies.

## Proposed Solution
#### 1. Detailed explanation of the proposed solution
*KrishiSetu-Connect* is an integrated agro-logistics and decentralized digital exchange platform:
* *Micro-Hub Pooling Network:* Uses existing Panchayat offices and Village Level Centers as decentralized aggregation nodes where smallholders drop harvest lots without needing dedicated transport.
* *Smart Forward-Contract Bidding:* Consumers, residential welfare associations (RWAs), and institutional buyers place bulk demand pools up to 10 days in advance, allowing farmers to harvest against pre-guaranteed contracts.
* *AI Demand-Logistics Orchestration:* Integrates local freight operators and mini-commercial pickup trucks into a dynamically routed mesh network that handles first-mile collection and city distribution within 12 hours.

#### 2. How it addresses the problem
* *Bypasses APMC & Middlemen Rings:* Connects farmer aggregates directly to bulk purchasers, removing the 4–5 tiers of agents, commission fees, and unloading cuts.
* *Reallocates the Price Margin:* Redirects 68–75% of retail price back to the producer while providing buyers produce at 15–20% below standard supermarket and neighborhood vendor rates.
* *Reduces Post-Harvest Wastage:* Dynamic grouping and pre-allocated transport minimize handling damage and keep transit times below 14 hours.

#### 3. Innovation and uniqueness of the solution
* *Reverse Route Backhaul Allocation:* The system automatically schedules returning intercity trucks and milk tankers with available capacity, lowering transit costs by up to 35%.
* *Computer-Vision Quality Assurance:* Farmers snap a photo of produce crates; an embedded computer vision model grades size, freshness, and defect levels to automatically assign quality grades without disputes.
* *Voice-Guided USSD/WhatsApp Engine:* Farmers can negotiate, list stocks, and receive settlement notifications using automated local-language voice prompts on low-cost feature phones or smartphones.

---
## Technical Approach
#### 1. Technologies to be used
* *Frontend:* React Native (cross-platform mobile apps for buyers and drivers), Web Dashboard (Next.js & Tailwind CSS for FPOs and admin management), WhatsApp Cloud API.
* *Backend:* Go (Golang) for fast microservices and matching engine; Python FastAPI for AI/ML inference.
* *Database & Cache:* PostgreSQL with PostGIS for spatial queries, Redis for real-time order locking and tracking.
* *AI / Machine Learning Stack:*
  * Demand Forecasting: NeuralProphet and XGBoost trained on regional APMC Mandi trends, commodity seasonality, and festival calendars.
  * Route Planning: VROOM / Google OR-Tools solving Multi-Depot Vehicle Routing with Time Windows (MDVRPTW).
  * Quality Grading: Lightweight YOLOv8 computer vision model running on cloud endpoints for produce surface-defect detection.
* *Infrastructure:* Docker, Kubernetes, AWS (S3, EC2), Mapbox API for navigation.
* #### 2. Methodology and process for implementation

[Farmer / FPO Listing]              [Bulk Buyer / RWA Group Demand]
│                                         │
▼                                         ▼
Crop Photo & Quantity                  Advance Scheduled Orders
│                                         │
└────────────────┬────────────────────────┘
▼
[KrishiSetu Matching Engine]
┌────────────────────────────────────────────────────────┐
│ • AI Produce Quality Grading (CV Model)                │
│ • Forward Demand Matching & Escrow Deposit             │
│ • First-Mile Hub Allocation Planner                    │
└────────────────────────┬───────────────────────────────┘
▼
[Dynamic Routing & Logistics]
┌────────────────────────────────────────────────────────┐
│ • MDVRPTW Route Optimization                           │
│ • Driver App Navigation & Vehicle Capacity Matching    │
│ • Transit Temperature & Delay Telemetry                │
└────────────────────────┬───────────────────────────────┘
▼
[Delivery & Escrow Release]
(Direct UPI Payout via Aadhaar Bridge)


1. *Digital Intake:* Farmers enter crop quantity via vernacular voice commands and upload crate photos for AI-based grading.
2. *Order Consolidation:* The matching engine pairs harvest estimates with city-buyer bulk orders and routes orders to the nearest local aggregation point.
3. *Optimized Dispatch:* Fleet drivers receive automated pick-and-drop waypoints optimized to prevent detours and minimize fuel usage.
4. *Instant Settlement:* Successful barcode/QR scan at the final drop point unlocks payment directly into the farmer's bank account via UPI.


## Feasibility and Viability
#### 1. Analysis of the feasibility of the idea
* *Low Initial Capital Expenditure:* Builds upon existing village infrastructure (Common Service Centers, PACS) rather than building new brick-and-mortar consolidation centers.
* *Technical Scalability:* The microservices architecture and cloud-hosted matching engine can easily scale across districts and states.
* *Economic Sustainability:* A modest platform convenience fee (2.5%) applied to buyer transactions covers cloud compute, driver incentives, and technical maintenance.

#### 2. Potential challenges and risks
* *Driver Reliability in Rural Belts:* Potential delays from informal drivers or lack of available freight during peak harvesting weeks.
* *Price Volatility:* Sudden open-market price spikes that might tempt farmers or buyers to default on forward contracts.
* *Network Connectivity Dead Zones:* Weak 4G signals in remote rural farmlands.

#### 3. Strategies for overcoming these challenges
* *Hybrid 3PL Partnerships:* Blend local mini-truck gig drivers with institutional logistics players (e.g., Delhivery, Porter, India Post) as backup capacity.
* *Escrow Guarantee Lock:* Smart-contract escrow deposits for buyers and performance-based incentive scoring for farmers to prevent default.
* *Offline-First App Architecture:* Mobile apps queue pickup records and weight receipts locally on SQLite and sync automatically when internet connectivity resumes.

## Impact and Benefits
#### 1. Potential impact on the target audience
* *Marginal and Small Farmers:* Immediate access to transparent retail pricing, cutting dependency on exploitative local money-lending commission agents.
* *Consumers and Bulk Buyers:* Access to farm-fresh produce within 24 hours of harvest at lower costs, with full source traceability.
* *Local Transporters:* Higher earnings via regular scheduled routes and reduced unpaid return trips.

#### 2. Benefits of the solution
* *Economic:* Increases farmer realization per quintal by *30–40%* while cutting consumer procurement costs by *15–20%*.
* *Social:* Enhances financial inclusion with instant, verifiable digital payments into Jan Dhan accounts; empowers FPO self-governance.
* *Environmental:* Lowers post-harvest rotting by *25%* and cuts vehicle emissions through full-capacity batch routing.



## Research and References
1. *Acharya, S. S. (2023):* Agricultural Marketing in India. Oxford & IBH Publishing (Analysis of farm-retail price spreads and marketing efficiency across perishable commodities).
2. *NITI Aayog Strategy Paper:* Doubling Farmers' Income through Efficient Value Chains and Tech-Enabled Logistics Integration.
3. *Ministry of Consumer Affairs, Food & Public Distribution:* Annual Report on Price Stabilization Measures and Agri-Logistics Improvements.
4. *Toth, P., & Vigo, D. (2014):* Vehicle Routing: Problems, Methods, and Applications. Society for Industrial and Applied Mathematics (SIAM).
5. *Open Network for Digital Commerce (ONDC):* Protocol Specifications for Agri-Value Chain Integration and Buyer-Seller Interoperability.
