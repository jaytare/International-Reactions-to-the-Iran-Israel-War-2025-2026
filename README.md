# International Reactions to the Iran–Israel War 2025–2026
### SQL analysis of how 210 countries and organisations 
responded to the Iran–Israel military conflict

---

## Objective
Analyse the global political reaction to the Iran–Israel 
war using structured stance data covering 210 countries 
and multilateral organisations. This project identifies 
alignment patterns, official statement activity and the 
divide between state and institutional responses.

---

## Dataset
- **Source:** Kaggle — Iran Israel War 2026 OSINT Dataset
- **File used:** international_reactions.csv
- **Coverage:** 210 countries and multilateral entities
- **Key field:** overall_stance — 9 categories including
  condemns_iran, supports_iran, silent, 
  calls_for_deescalation, active_participant_coalition

---

## Key Findings

### The silence majority
The single largest group was **silent nations — 68 countries** 
chose not to issue any public stance on the conflict. 
More countries said nothing than condemned Iran, 
revealing a deeply divided and cautious international 
community.

### Western coalition vs Iran
**50 countries condemned Iran** while only **4 openly 
supported Iran** — reflecting Iran's significant 
diplomatic isolation. The condemning bloc was largely 
Western and NATO-aligned.

### EU unity
**22 out of 27 EU member states condemned Iran** — 
showing near-unanimous European alignment against 
Iran's military actions.

### Active combatants
**11 entities became active participants** in the 
conflict including the US, UK, Jordan and Israel — 
confirming this escalated well beyond a bilateral 
Iran-Israel exchange into a broader regional war.

### Multilateral organisations prioritised peace
**58.82% of multilateral organisations** such as the UN 
and regional bodies called for de-escalation rather 
than taking sides — contrasting sharply with individual 
state behaviour where 24.35% of states condemned Iran.

### Data quality note
Israel appears under supports_israel rather than 
active_participant_coalition in the dataset — flagged 
as a classification issue in the source data.

---

## SQL Techniques Demonstrated
- `GROUP BY` with `COUNT` and percentage calculations
- `CASE WHEN` for boolean aggregations
- `PRAGMA table_info` for schema inspection
- Window functions `OVER (PARTITION BY)` 
- CTEs (`WITH`) for multi-step analysis

---

## Business Questions Answered

| # | Question | Answer |
|---|---|---|
| 1 | What was the dominant global stance? | Silence — 68 countries |
| 2 | How did EU respond vs rest of world? | 22/27 EU condemned Iran |
| 3 | Which countries were active combatants? | 11 including US, UK, Jordan |
| 4 | Which stance issued most statements? | Condemn Iran bloc |
| 5 | How did multilateral orgs differ from states? | Orgs favoured de-escalation 58.82% vs states 24.35% |

---

## Repo Structure
```
social-media-iran-israel/
├── README.md
├── data/
│   └── international_reactions_cleaned.csv
├── queries/
│   ├── 01_global_stance_breakdown.sql
│   ├── 02_eu_vs_noneu_stance.sql
│   ├── 03_active_combatants.sql
│   ├── 04_official_statements.sql
│   └── 05_state_vs_multilateral_cte.sql
└── screenshots/
    ├── query1_global_stance.png
    ├── query2_eu_vs_noneu.png
    ├── query3_combatants.png
    ├── query4_statements.png
    └── query5_cte_entity_type.png
```

---

*Data source: Kaggle — Iran Israel War 2026 OSINT Dataset 
by Daniel Rosehill — public domain research dataset*
