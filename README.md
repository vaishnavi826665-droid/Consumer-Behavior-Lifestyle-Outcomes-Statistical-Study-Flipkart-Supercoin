# Consumer-Behavior-Lifestyle-Outcomes-Statistical-Study-Flipkart-Supercoin
Simulated end-to-end analytics project modeling a SuperCoin-style rewards platform: engagement monitoring dashboards, a growth roadmap intervention, and a behavioral clustering model that infers user lifestyle segments purely from reward activity (no survey data).
Simulated end-to-end analytics project modeling a SuperCoin-style rewards platform: engagement
monitoring dashboards, a growth roadmap intervention, and a behavioral clustering model that
infers user lifestyle segments purely from reward activity (no survey data).


Data disclosure: All data in this project is synthetically generated (numpy/pandas,
seeded for reproducibility) to realistically mimic a rewards-platform dataset. No real
Flipkart or third-party data was used or accessed.



Project Goals


Executive dashboard impact — quantify how much faster decisions get made once raw data
is turned into a monitoring dashboard (Tableau / Power BI style) vs. manual Excel reporting.
Growth roadmap impact — quantify the engagement lift from a targeted rewards/roadmap
strategy pitch (Miro / PowerPoint planning artifact).
Behavior → lifestyle inference — test whether a user's lifestyle type can be recovered
from nothing but their reward-earning and redemption behavior, using unsupervised clustering.


Key Results

MetricResultReduction in executive decision-making time~25% (paired t-test, p < 0.001)Lift in platform engagement post-roadmap~18% (paired t-test, p < 0.001)Lifestyle segment recovery from behavior aloneAdjusted Rand Index well above 0 (K-Means)


Methodology


Synthetic data generation — 4,000 simulated users assigned a hidden "lifestyle archetype"
(Deal Hunter, Convenience Seeker, Wellness Focused, Tech Enthusiast), each with a distinct
behavioral fingerprint (login frequency, coins earned/redeemed, redemption category).
Before/after simulation — engagement scores and executive decision times are modeled
pre- and post-intervention, tested for significance with paired t-tests.
Unsupervised clustering — K-Means is run on only behavioral features (no archetype
labels) and compared back against the true labels via Adjusted Rand Index, to test whether
lifestyle segments are recoverable from behavior alone.


Repo Structure

.
├── notebooks/
│   └── consumer_behavior_lifestyle_study.ipynb   # full analysis, pre-executed with outputs
├── dashboard/
│   └── index.html                                # standalone interactive dashboard (Chart.js)
├── reports/
│   └── Consumer_Behavior_Lifestyle_Outcomes_Report.docx   # formal written report
├── data/
│   ├── supercoin_user_activity.csv               # synthetic user-level dataset
│   └── decision_time_log.csv                     # synthetic decision-time log
├── images/                                       # exported chart previews for this README
├── requirements.txt
└── README.md

Interactive Dashboard

dashboard/index.html is a standalone, no-build-step dashboard (HTML + Chart.js via CDN) that
mirrors the KPIs an executive would see in the real Tableau/Power BI monitoring setup: engagement
trend, decision-time reduction, segment lift, and redemption mix. Open it directly in a browser,
or enable GitHub Pages on this repo (Settings → Pages → deploy from main /root or /dashboard)
to get a shareable live link.

Written Report

reports/Consumer_Behavior_Lifestyle_Outcomes_Report.docx is a formal write-up (objectives,
methodology, results, limitations, recommendations) suitable for sharing with stakeholders who
want the findings without opening the notebook.

Running It

bashgit clone <this-repo-url>
cd consumer-behavior-lifestyle-study
pip install -r requirements.txt
jupyter notebook notebooks/consumer_behavior_lifestyle_study.ipynb

The notebook is deterministic (np.random.seed), so re-running it reproduces the exact same
numbers and charts shown here.

Tools & Techniques

Python · pandas · NumPy · scikit-learn (KMeans, StandardScaler) · scipy.stats
(paired t-tests) · matplotlib / seaborn — standing in for the Tableau / Power BI / Miro
tools used in the original workflow.

License

MIT — see LICENSE.
