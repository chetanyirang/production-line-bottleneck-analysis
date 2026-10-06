---
license: cc-by-nc-4.0
task_categories:
  - tabular-classification
  - tabular-regression
  - time-series-forecasting
language:
  - en
tags:
  - synthetic
  - manufacturing
  - oee
  - overall-equipment-effectiveness
  - line-performance
  - takt-time
  - cycle-time
  - bottleneck-analysis
  - theory-of-constraints
  - toc
  - lean-manufacturing
  - six-big-losses
  - tpm
  - total-productive-maintenance
  - nakajima
  - goldratt
  - womack
  - mes
  - manufacturing-execution-system
  - iso-22400
  - semi-e10
  - shift-performance
  - mtbf
  - mttr
  - first-pass-yield
  - value-added-ratio
  - lean-six-sigma
  - throughput-optimization
  - changeover
  - smed
pretty_name: "MFG-005 — Manufacturing Line Performance Dataset (Sample)"
size_categories:
  - 1K<n<10K
---

# MFG-005 — Manufacturing Line Performance Dataset (Sample)

A schema-identical preview of **MFG-005**, the XpertSystems.ai synthetic
**shift-level manufacturing line performance** dataset for OEE ML,
Theory of Constraints bottleneck analysis, Six Big Losses prediction,
Lean Six Sigma improvement targeting, MES analytics, and Industrie 4.0
production research. The full product covers 10,000-100,000 records.
This sample is HF-sized at 3,000 records.

> **Built by** XpertSystems.ai — Synthetic Data Platform
> **Contact** [pradeep@xpertsystems.ai](mailto:pradeep@xpertsystems.ai) · [xpertsystems.ai](https://xpertsystems.ai)
> **License** CC-BY-NC-4.0 (sample); commercial license available for the full product.

---

## What MFG-005 does — completing the 5-SKU Manufacturing vertical

MFG-005 is the **fifth Manufacturing & Industrial Systems SKU** in the
XpertSystems catalog, completing a comprehensive Manufacturing vertical
covering BOTH reliability engineering AND quality + operations
management:

| SKU | Domain | Granularity | Primary Audience |
|---|---|---|---|
| MGG-001 | Reliability — sensor streams | 1-min to 1-hr | IIoT, anomaly detection |
| MFG-002 | Reliability — failure events | One row per event | CMMS, reliability engineering |
| MFG-003 | Reliability — RUL training | Multi-obs per asset | PdM ML, PHM Society |
| MFG-004 | Quality — inspection records | One row per inspection | QMS, SPC, MSA, 6 Sigma |
| **MFG-005** | **Operations — line performance** | **One row per shift × line** | **MES, OEE, TPM, Lean** |

Where MFG-004 captures **per-part quality** (inspection-record granularity),
MFG-005 captures **per-shift line performance** (production-system
granularity). This is the data shape that flows into MES (Manufacturing
Execution Systems) like Rockwell PlantPAx, Siemens Opcenter (formerly
SIMATIC IT), GE Digital Plant Applications (formerly Proficy),
Wonderware MES (AVEVA), Honeywell Forge, and SAP Digital Manufacturing.

| Buyer Persona | Use Case |
|---|---|
| **MES Vendors (Rockwell, Siemens Opcenter, GE Digital, AVEVA Wonderware, Honeywell Forge, SAP DM)** | OEE/TPM workflow training data |
| **OEE Software (Vorne XL, FactoryTalk Analytics, OEE Toolkit)** | OEE benchmarking + Six Big Losses ML |
| **Lean Manufacturing Consultancies (Toyota, Shingo Institute, Lean Enterprise Institute)** | OEE improvement case-study data |
| **TPM (Total Productive Maintenance) Programs** | Six Big Losses framework training |
| **Theory of Constraints (TOC) Practitioners (Goldratt Institute)** | Bottleneck analysis ML |
| **Lean Six Sigma (Shingo / TPS)** | Value-added ratio improvement targeting |
| **Production Engineering** | Takt time vs cycle time optimization |
| **SMED (Single-Minute Exchange of Die)** | Changeover time reduction |
| **Industrie 4.0 / Smart Factory** | Digital twin training data |
| **Energy Management (ISO 50001)** | Energy per good unit ML |

This is the substrate **MES vendors, OEE software companies, Lean Six
Sigma consultancies, Theory of Constraints practitioners, TPM programs,
and Industrie 4.0 research programs** have been waiting for: a coherent
shift-level line performance dataset where OEE A×P×Q decomposition ×
Six Big Losses × bottleneck utilization × cycle time vs takt time × FPY
× energy × cost all interact with **Nakajima 1988 / Goldratt 1984 /
Womack 1990 / SEMI E10 / ISO 22400-grade calibration**.

---

## What's inside — five related CSV files

MFG-005 is a **multi-output relational** dataset with five CSVs sharing
`line_id` as join key.

| File | Rows (sample) | Columns | Size |
|---|---:|---:|---|
| `mfg005_synthetic_line_performance.csv` | 3,000 | 118 | ~2.3 MB |
| `throughput_vs_takt.csv` | 3,000 | 11 | ~316 KB |
| `bottleneck_analysis_report.csv` | 235 | 5 | ~14 KB |
| `oee_summary_by_line.csv` | 36 | 9 | ~5 KB |
| `downtime_pareto.csv` | 6 | 3 | ~360 B |

Plus `mfg005_metadata.json` with run configuration.

Schemas are provided in five matching JSON files.

### Main schema module structure (118 columns total)

| Module | Cols | Coverage |
|---|---:|---|
| Line identity | 16 | line_id, plant_id, work_center_id, shift_id, date, shift number, duration, product_id, family, line_type, automation level, stations, configuration, plant location, sector, production order |
| Cycle time | 14 | takt time, designed CT, actual CT avg/std/min/max, P50/P95, CoV, bottleneck station + CT + util, secondary bottleneck, CT loss |
| Production volume | 14 | planned/actual quantity, good/defective/scrap/rework units, throughput actual/design UPH, ratio, RTY, total parts, WIP queue avg/max, output variance, UPH per operator |
| OEE (Nakajima 1988) | 13 | planned production time, available time, A/P/Q components, OEE overall, TEEP, Loading, A/P/Q losses, Six Big Losses breakdown, OEE benchmark class, primary loss driver |
| Changeover & downtime | 17 | changeover time + count, unplanned/planned DT, DT events, MTBF, MTTR, largest DT, equipment failure flag, 6 downtime categories (mech/elec/tool/material/operator/quality), planned maintenance, last maintenance type |
| Equipment | 2 | age years, condition score |
| Operator | 10 | headcount planned/actual, utilization, skill level avg, absenteeism, overtime, ergonomic incidents, variance flag, cross-training ratio, supervisor |
| Quality | 11 | defect rate PPM, sigma level, Cpk + Cp primary, primary + secondary defect type, inspection method, SPC chart flag, OOC flag, quality alert, customer complaint, FPY, RFT |
| Energy & sustainability | 7 | energy kWh + per good unit, peak demand, compressed air, coolant, energy efficiency, carbon footprint |
| Cost | 12 | direct labour, overhead, material per unit, scrap, rework, downtime cost per min + total, COPQ, value-added ratio, production cost per unit |

---

## Calibration sources

Every distribution is anchored to **named manufacturing engineering
standards or canonical frameworks**. The headline anchors are
**Nakajima 1988** (Total Productive Maintenance / OEE framework),
**Goldratt 1984** (Theory of Constraints), and **Womack 1990 Lean
Thinking**. Other anchors:

- **Nakajima 1988 Introduction to TPM** — Six Big Losses framework
  (equipment failure, setup/adjustment, idling/minor stops, reduced
  speed, process defects, startup yield loss); OEE = A × P × Q
  decomposition.
- **Goldratt 1984 The Goal + Theory of Constraints** — bottleneck
  identification, drum-buffer-rope synchronization, throughput
  optimization.
- **Womack 1990 The Machine That Changed the World + Lean Thinking** —
  value-added ratio, 8 wastes (muda), value stream mapping.
- **Ohno 1988 Toyota Production System** — takt time, standard work,
  cycle time stability.
- **SEMI E10 Standard** — equipment performance metrics for
  semiconductor manufacturing.
- **ISO 22400-1/-2** — KPIs for manufacturing operations management
  (OEE, NEE, OEE_PR, Quality Rate).
- **ANSI/ISA-95** — enterprise-control system integration.
- **SAE J4000** — Identification and Measurement of Best Practice in
  Implementation of Lean Operation.
- **ARC Advisory Group + SME (Society of Manufacturing Engineers)
  Industry Benchmarks** — OEE/availability/performance benchmarks by
  sector.
- **Shingo Prize Model + Toyota Production System** — operational
  excellence assessment framework.
- **AIAG / VDA standards** — automotive manufacturing benchmarks.
- **SMED (Single-Minute Exchange of Die) — Shingo 1985** — changeover
  time reduction methodology.
- **ISO 50001** — energy management systems for manufacturing.
- **Pyzdek 2003 Six Sigma Handbook + Motorola 1986** — sigma level
  framework for manufacturing line quality.

---

## Validation scorecard

The wrapper ships a 10-metric Nakajima/TOC/Lean/ISO 22400-anchored
scorecard (`validation_scorecard.json`) that re-scores the dataset on
every generation. Default seed 42 result:

| ID | Metric | Target | Observed | Source |
|---|---|---|---:|---|
| M01 | OEE Overall Mean | 0.53–0.77 | **0.653** | **Nakajima 1988 / ARC / SME** |
| M02 | OEE Availability | 0.75–0.95 | **0.858** | **Nakajima 1988 / SMRP** |
| M03 | OEE Quality (FLOOR ≥95%) | ≥0.95 | **0.994** | **Nakajima 1988 / Six Sigma** |
| M04 | Bottleneck Utilization % | 82–102 | **95.01** | **Goldratt 1984 TOC** |
| M05 | World-Class OEE Share (≥0.85) | 0.00–0.20 | **0.065** | Nakajima 1988 / ARC |
| M06 | Performance Loss Primary Driver | 0.40–0.90 | **0.752** | **Six Big Losses / TPM** |
| M07 | Sigma Level Mean (FLOOR ≥2.5σ) | ≥2.5σ | **4.67σ** | Motorola 1986 / ASQ |
| M08 | Throughput Ratio | 0.60–1.00 | **0.819** | **ISO 22400-2 / SEMI E10** |
| M09 | Cycle Time CoV (CEILING ≤0.23) | ≤0.23 | **0.094** | **Lean / Toyota Production System** |
| M10 | Value-Added Ratio % (FLOOR ≥25%) | ≥25% | **50.10** | **Womack 1990 Lean Thinking** |

**Grade: A+ (100/100). Verified across seeds 42, 7, 123, 2024, 99, 1.**

**Standout calibration depth — this is the most precisely-centered
Manufacturing SKU**:
- **M01 OEE 65.28% vs target 65%** — *0.28pp deviation* 🎯
- **M02 Availability 85.84% vs target 85%** — *0.84pp deviation* 🎯
- **M10 Value-added ratio 50.10% vs Womack target 50%** — *0.10pp deviation* 🎯
- **M08 Throughput ratio 0.819 vs target 0.80** — *1.9pp deviation*

**OEE A×P×Q math verifies**: 0.858 × 0.763 × 0.994 = **0.651** (matches
observed OEE 0.653 within rounding).

**OEE by sector** reproduces published Nakajima benchmarks:
- Medical 0.69, Pharma 0.67, Industrial 0.65, Electronics 0.66,
  Automotive 0.64, Food/Bev 0.65

**Six Big Losses primary driver** matches TPM textbook: performance_loss
75% / availability_loss 25% / quality_loss <1% (mature plants are
performance-bound, not availability-bound or quality-bound).

---

## Suggested use cases

- **OEE prediction ML** — line characteristics + shift features ×
  OEE overall prediction (regression).
- **Six Big Losses classification** — multi-class classifier for
  primary OEE loss driver (equipment failure / setup / idling /
  reduced speed / process defects / startup yield).
- **Bottleneck identification (TOC)** — line topology + cycle times
  × bottleneck station prediction.
- **Takt time vs cycle time gap analysis** — designed CT + automation
  + skill × actual CT prediction.
- **Throughput optimization** — actual/design UPH ratio prediction
  for capacity planning.
- **Changeover time reduction (SMED)** — changeover_time +
  changeover_count × throughput impact modeling.
- **Lean value-added improvement** — value_added_ratio × waste
  category for 8-wastes (muda) prioritization.
- **Energy efficiency benchmarking** — energy_per_good_unit + peak
  demand × sector for ISO 50001 EnPI baselining.
- **Cost-of-poor-quality modeling** — scrap + rework + COPQ × defect
  type × economic outcomes.
- **Downtime Pareto analysis** — 6 downtime category aggregates ×
  improvement targeting (mechanical-dominant lines vs
  electrical-dominant).
- **Operator productivity** — headcount + skill_level + cross-training
  × OEE for HR + Lean training ROI modeling.

---

## Loading

```python
from datasets import load_dataset

main = load_dataset(
    "xpertsystems/mfg005-sample",
    data_files="mfg005_synthetic_line_performance.csv",
    split="train",
)
oee_summary = load_dataset(
    "xpertsystems/mfg005-sample",
    data_files="oee_summary_by_line.csv",
    split="train",
)
```

Or with pandas directly:

```python
import pandas as pd
from huggingface_hub import hf_hub_download

main_path = hf_hub_download(
    repo_id="xpertsystems/mfg005-sample",
    filename="mfg005_synthetic_line_performance.csv",
    repo_type="dataset",
)
df = pd.read_csv(main_path)

# OEE A×P×Q decomposition by sector
for sector, sub in df.groupby("industry_sector"):
    a = sub["oee_availability"].mean()
    p = sub["oee_performance"].mean()
    q = sub["oee_quality"].mean()
    oee = sub["oee_overall"].mean()
    print(f"{sector:14s}: OEE={oee:.3f} = A({a:.3f}) × P({p:.3f}) × Q({q:.3f})")

# Six Big Losses primary driver distribution
print(df["oee_loss_primary_driver"].value_counts(normalize=True))

# Bottleneck utilization by line type (TOC)
bn_by_type = df.groupby("line_type")["bottleneck_utilisation_pct"].mean()
print(bn_by_type.sort_values(ascending=False))
```

Five schema JSON files are bundled for pipeline integration:

```python
import json
schema_main = json.load(open("MFG_005_main_schema.json"))
schema_oee = json.load(open("MFG_005_oee_summary_schema.json"))
schema_bn = json.load(open("MFG_005_bottleneck_schema.json"))
schema_takt = json.load(open("MFG_005_throughput_schema.json"))
schema_dt = json.load(open("MFG_005_downtime_pareto_schema.json"))
```

This dataset is **cross-sectional with shift-level granularity** —
one row per shift × line, ordered by shift_date but not strictly
longitudinal per asset. For time-series shift trend analysis, group
by `line_id` and sort by `shift_date`.

---

## Schema highlights

**Line identity** — `line_id`, `plant_id`, `work_center_id`, `shift_id`,
`shift_date`, `shift_number` ∈ {1, 2, 3}, `shift_duration_minutes`,
`product_id`, `product_family`, `production_order_id`, `line_type` ∈
{assembly_line, machining_cell, packaging_line, fabrication,
chemical_process, discrete_manufacturing, batch_process,
continuous_process, hybrid}, `automation_level` ∈ {manual,
semi_automated, highly_automated, lights_out, cobotic},
`number_of_stations`, `line_configuration` ∈ {serial, parallel,
u_shaped, flexible, transfer_line, job_shop}, `plant_location` (12
global locations), `industry_sector` ∈ {automotive, electronics,
pharma, food_bev, aerospace, industrial, consumer, medical, chemical,
packaging}.

**Cycle time** — `takt_time_seconds`, `designed_cycle_time_seconds`,
`actual_cycle_time_avg_seconds`, std/min/max, P50/P95, `cycle_time_cov`,
`bottleneck_station_id`, `bottleneck_cycle_time_seconds`,
`bottleneck_utilisation_pct`, `secondary_bottleneck_station_id`,
`cycle_time_loss_seconds`.

**Production volume** — `planned_production_quantity`,
`actual_production_quantity`, `good_units_produced`,
`defective_units_produced`, `scrap_units`, `rework_units`,
`throughput_rate_actual_uph`, `throughput_rate_design_uph`,
`throughput_rate_ratio`, `rolled_throughput_yield_pct`,
`total_parts_processed`, `wip_queue_avg_units`, `wip_queue_max_units`,
`output_variance_pct`, `units_per_operator_hour`.

**OEE (Nakajima 1988)** — `planned_production_time_minutes`,
`available_time_minutes`, `oee_availability`, `oee_performance`,
`oee_quality`, `oee_overall`, `teep_pct`, `loading_pct`,
`availability_loss_minutes`, `performance_loss_units`,
`quality_loss_units`, `six_big_losses_breakdown`, `oee_benchmark_class`
∈ {world_class, good, average, poor}, `oee_loss_primary_driver` ∈
{availability_loss, performance_loss, quality_loss}.

**Changeover & downtime** — `changeover_time_minutes`,
`changeover_count`, `downtime_unplanned_minutes`,
`downtime_planned_minutes`, `downtime_event_count`, `mtbf_minutes`,
`mttr_minutes`, `largest_downtime_event_minutes`,
`equipment_failure_flag`, `downtime_category_mechanical`,
`downtime_category_electrical`, `downtime_category_tooling`,
`downtime_category_material`, `downtime_category_operator`,
`downtime_category_quality_hold`, `planned_maintenance_flag`,
`maintenance_type_last` ∈ {predictive, preventive, corrective,
emergency}.

**Equipment** — `equipment_age_years`, `equipment_condition_score`.

**Operator** — `operator_headcount_planned`, `operator_headcount_actual`,
`operator_utilisation_pct`, `operator_skill_level_avg` ∈ {trainee,
semi_skilled, skilled, expert, multi_skilled}, `absenteeism_rate_pct`,
`overtime_hours`, `ergonomic_incident_flag`, `operator_variance_flag`,
`cross_training_ratio_pct`, `shift_supervisor_id`.

**Quality** — `defect_rate_ppm`, `sigma_level`,
`cpk_primary_characteristic`, `cp_primary_characteristic`,
`primary_defect_type`, `secondary_defect_type`, `inspection_method`,
`spc_control_chart_flag`, `control_chart_out_of_control`,
`quality_alert_issued`, `customer_complaint_flag`,
`first_pass_yield_pct`, `right_first_time_pct`.

**Energy & sustainability** — `energy_consumption_kwh`,
`energy_per_good_unit_kwh`, `peak_demand_kw`,
`compressed_air_consumption_m3`, `coolant_consumption_litres`,
`energy_efficiency_score`, `carbon_footprint_kg_co2`.

**Cost** — `direct_labour_cost_usd`, `overhead_cost_usd`,
`material_cost_per_unit_usd`, `scrap_cost_usd`, `rework_cost_usd`,
`downtime_cost_per_minute_usd`, `total_downtime_cost_usd`,
`cost_of_poor_quality_usd`, `value_added_ratio_pct`,
`production_cost_per_unit_usd`.

---

## Calibration notes & limitations

In the spirit of honest synthetic data, a few things buyers of the sample
should know:

1. **Industry sector mix is skewed at n=3,000**. Only 6 of 10 configured
   sectors are well-represented (industrial 38%, electronics 24%,
   automotive 22%, with smaller pharma/medical/food-bev shares). The
   full product (10K-100K records) distributes evenly across all 10
   sectors. For sector-specific modeling at this sample size, filter
   carefully or use the full product.

2. **TEEP averages 20.3% and Loading 31.1%** — both significantly below
   typical 24/7 plant values. TEEP = OEE × Loading; the generator's
   Loading parameter reflects partial-utilization plants (e.g., 1-2
   shifts/day rather than continuous 3-shift). For 24/7 continuous-
   process plants, the full product supports configurable Loading
   targets.

3. **Quality component of OEE is 99.36%** (very high). Real-world OEE
   quality components vary: world-class >99%, typical 95-99%, low-yield
   <95%. The generator centers Quality at the upper end; for lower-yield
   modeling (electronics PCB rework, pharmaceutical batch yield), the
   full product calibrates per sector.

4. **Absenteeism averages 8.5%** — above typical industrial 3-5%. The
   generator's absenteeism model is skewed slightly high; for benchmark
   absenteeism modeling, target 3-5% in the full product configuration.

5. **Scrap cost ($2/shift) and rework cost ($9/shift) are very low** in
   absolute terms because they're rolled up into the broader COPQ
   metric ($1,901/shift). For per-event cost modeling, use the COPQ
   composite rather than the scrap/rework components individually.

6. **OEE by automation level is non-monotonic**: cobotic 0.69 > lights_out
   0.68 ≈ manual 0.68 > semi-auto 0.65 > highly_auto 0.62. This
   reflects the real-world observation that highly-automated lines
   often have more downtime than well-run manual lines — automation
   amplifies both performance AND failure modes. For automation-ROI
   modeling, this non-monotonicity is realistic.

7. **Cycle time exceeds takt time on 81% of shifts** (CT > takt). This
   is realistic — most production lines run slower than designed takt
   under real-world conditions (downtime, setup, quality losses). The
   takt time represents customer-demand-driven design rate; actual CT
   includes all losses.

8. **MTBF 199 minutes / MTTR 17 minutes** — realistic shift-level
   reliability metrics. Different from MFG-002/MFG-003 which use
   hours-scale MTBF (asset-level vs shift-level reliability differs).

9. **6 downtime categories show realistic Pareto** (mechanical 30 min >
   electrical 12 > tooling 8 > quality 5 > material 5 > operator 2).
   Mechanical dominance reflects rotating-equipment-heavy fleet; for
   electronics/assembly lines, the full product supports different
   downtime Pareto profiles.

10. **Deterministic seeding.** Wrapper invokes the generator via
    subprocess with explicit `--seed` parameter. Seed sweep verifies
    Grade A+ across {42, 7, 123, 2024, 99, 1}.

---

## Commercial / full product

The full **MFG-005** product covers 10,000-100,000 shift records with
configurable `--automation_profile` (modern_greenfield /
brownfield_mixed / manual_intensive / lights_out), `--oee_target_class`
(world_class / good / average / poor / mixed), refined sector-specific
OEE benchmarks per Nakajima 1988 published targets, configurable
absenteeism profiles per region (US/EU/APAC industrial benchmarks),
24/7 vs 2-shift vs 1-shift Loading configurations, pre-built feature
engineering pipelines for OEE prediction ML (shift lag features,
rolling MTBF/MTTR, seasonal patterns), Industrie 4.0 / smart factory
extension columns (digital twin sync flags, edge compute latency,
OPC-UA tag counts), and energy management ISO 50001 baseline /
performance period decomposition for EnPI tracking. Available under
commercial license — contact
[pradeep@xpertsystems.ai](mailto:pradeep@xpertsystems.ai).

XpertSystems.ai also publishes synthetic data products across **Oil &
Gas** (17 SKUs, OREDA/ISO 14224/API/IPIECA standards),
**Healthcare/Neurology** (10 SKUs, ENROLL-HD/PRO-ACT/TRACK-HD/CLARITY-AD
clinical trial calibration), and **Manufacturing** (5 SKUs covering
reliability engineering AND quality + operations management):

- **MGG-001**: Factory Sensor Dataset (IIoT sensor streams)
- **MFG-002**: Machine Failure Event Records (CMMS, ISO 14224)
- **MFG-003**: Predictive Maintenance Dataset (RUL ML training)
- **MFG-004**: Quality Control Dataset (SPC, MSA, 6 Sigma)
- **MFG-005**: Manufacturing Line Performance (OEE, TPM, Lean) — this SKU

Catalog: [huggingface.co/xpertsystems](https://huggingface.co/xpertsystems).
