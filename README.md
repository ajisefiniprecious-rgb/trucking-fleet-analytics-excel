# Trucking Fleet & Freight Analytics — Excel Capstone Project

An end-to-end analytics workbook for a freight trucking operation, covering revenue, customers, routes, drivers, fleet maintenance, fuel spend, and safety — built entirely in Excel using PivotTables, PivotCharts, and cross-sheet formulas.

## Overview

This workbook models a multi-table relational dataset for a trucking/freight company and rolls it up into a single Executive Dashboard. It covers ~85,000 loads, ~85,000 trips, and 100,000+ delivery and fuel events across 121 trucks and 1,000 drivers, with supporting tables for customers, routes, facilities, maintenance, and safety incidents.

## Executive Dashboard

The `Executive Dashboards` sheet surfaces top-line KPIs, each driven by a live formula referencing the underlying data tables (not hardcoded values):

| KPI | Formula basis |
|---|---|
| Total Revenue | `SUM` of all load revenue |
| Total Loads | `COUNTA` of load records |
| Average Revenue Per Load | `AVERAGE` of load revenue |
| On-time Delivery % | `COUNTIF` of on-time delivery events |
| Avg Fleet MPG | `AVERAGE` of trip fuel efficiency |
| Active Drivers | `COUNTIF` of drivers with Active status |
| Total Fuel Spend | `SUM` of fuel purchase costs |
| Total Incidents | `COUNTA` of safety incident records |

It also includes 9 PivotCharts:
- Monthly Revenue Trend
- Revenue by Customer Type
- Top 10 Customers (by revenue)
- Top 10 Routes (by revenue)
- Driver Revenue
- Maintenance Cost by Type
- Safety Incidents (by type)
- Fuel Spend Trend
- Top 10 Drivers by Trip Count

## Data Model

16 sheets, organized as one fact-table-style core (`loads`, `trips`) surrounded by reference tables:

- **customers** — account details, contract type, credit terms
- **loads** — individual freight bookings (revenue, weight, route, status)
- **trucks** — fleet vehicle details
- **trips** — actual dispatch records linking loads, drivers, and trucks
- **routes** — standard origin/destination lanes and base rates
- **drivers** — driver roster and employment details
- **facilities** — pickup/delivery locations
- **delivery_events** — pickup/delivery timing and on-time tracking
- **safety_incidents** — incident records with cost and fault details
- **fuel_purchases** — fuel transactions by trip
- **maintenance_records** — service history by truck
- **truck_utilization_metrics** / **driver_monthly_metrics** — pre-aggregated monthly rollups
- **Pivot Tables** — supporting pivot table output for the dashboard charts
- **Data Dictionary** — full field-by-field reference for every table (see below)

A **Data Dictionary** sheet has been added covering every field in every table, plus notes on dataset provenance and on the relationship between the `booking_type` and `customer_type` fields in the `loads` sheet.

## Skills Demonstrated

- Multi-table relational data modeling in Excel
- PivotTables and PivotCharts across 11 distinct pivot caches
- Cross-sheet formulas (`SUM`, `AVERAGE`, `COUNTA`, `COUNTIF`) for live KPIs
- Dashboard design consolidating 9 visualizations on a single executive view
- Data documentation (data dictionary) for a complex, multi-sheet workbook

## Files in This Repo

- `TSA_CAPSTONE_PROJECT_AJISEFINI_PRECIOUS.xlsx` — the full workbook

## How to View

Open the file in Excel or Google Sheets. Start on the `Executive Dashboards` tab for the high-level view, then check the `Data Dictionary` tab for a full breakdown of every table and field before digging into the raw data sheets.

> Note: this file is large (~49MB) due to the volume of underlying data and pivot caches — GitHub will preview it but large-file hosting limits may apply on some plans.
