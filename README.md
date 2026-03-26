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
- **File used:** international_reactions_cleaned.csv
- **Coverage:** 210 countries and multilateral entities
- **Key field:** overall_stance — 9 categories including
  condemns_iran, supports_iran, silent, 
  calls_for_deescalation, active_participant_coalition

---

## Key Findings

### Query 1 — Global stance breakdown
The single largest group was **silent nations — 68 countries** 
chose not to issue any public stance on the conflict. 
More countries said nothing than condemned Iran, 
revealing a deeply divided and cautious international 
community.

![Global Stance Breakdown](screenshots/query1_global_stance.png)

---

### Query 2 — EU vs non-EU stance comparison
**22 out of 27 EU member states condemned Iran** — 
showing near-unanimous European alignment against 
Iran's military actions.

![EU vs Non-EU Stance](screenshots/query2_eu_vs_noneu.png)

---

### Query 3 — Active combatants
**11 entities became active participants** in the 
conflict including the US, UK, Jordan and Israel — 
confirming this escalated well beyond a bilateral 
Iran-Israel exchange into a broader regional war.

> **Data quality note:** Israel appears under 
> supports_israel rather than active_participant_coalition 
> — flagged as a classification issue in the source data.

![Active Combatants](screenshots/query3_combatants.png)

---

### Query 4 — Official statements by stance
Shows which stance categories issued the most 
official statements across head of state, head of 
government and foreign ministry channels.

![Official Statements](screenshots/query4_statements.png)

---

### Query 5 — State vs multilateral organisations (CTE)
**58.82% of multilateral organisations** called for 
de-escalation rather than taking sides — contrasting 
sharply with individual states where 24.35% condemned 
Iran. International institutions consistently prioritised 
peace over alignment.

![State vs Multilateral](screenshots/query5_cte_entity_type.png)

---

## Summary of Findings

| # | Question | Answer |
|---|---|---|
| 1 | Dominant global stance? | Silence — 68 countries |
| 2 | How did EU respond? | 22/27 EU condemned Iran |
| 3 | Active combatants? | 11 including US, UK, Jordan |
| 4 | Most statements issued by? | Condemn Iran bloc |
| 5 | Orgs vs states? | Orgs favoured de-escalation 58.82% |

---

## Key Insight
While Western nations and EU member states largely 
condemned Iran, the global majority chose silence — 
suggesting that outside the Western alliance, most 
countries preferred not to take a public position on 
the conflict. Multilateral organisations consistently 
called for de-escalation rather than alignment, 
reflecting institutional preference for diplomacy 
over confrontation.

---

## SQL Techniques Demonstrated
- `GROUP BY` with `COUNT` and percentage calculations
- `CASE WHEN` for boolean aggregations
- `PRAGMA table_info` for schema inspection
- Window functions `OVER (PARTITION BY)`
- CTEs (`WITH`) for multi-step analysis

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
