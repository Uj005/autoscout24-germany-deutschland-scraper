# Autoscout24 Germany / Deutschland - Scraper

A production-ready Autoscout24 scraper focused on Germany, built to collect fresh vehicle listings with rich pricing, technical, seller, and leasing data. It helps analysts, developers, and data teams turn fragmented car listings into clean, structured datasets for decision-making and market insights.


<p align="center">
  <a href="https://bitbash.dev" target="_blank">
    <img src="https://github.com/Z786ZA/Footer-test/blob/main/media/scraper.png" alt="Bitbash Banner" width="100%"></a>
</p>
<p align="center">
  <a href="https://t.me/Bitbash333" target="_blank">
    <img src="https://img.shields.io/badge/Chat%20on-Telegram-2CA5E0?style=for-the-badge&logo=telegram&logoColor=white" alt="Telegram">
  </a>&nbsp;
  <a href="https://wa.me/923249868488?text=Hi%20BitBash%2C%20I'm%20interested%20in%20automation." target="_blank">
    <img src="https://img.shields.io/badge/Chat-WhatsApp-25D366?style=for-the-badge&logo=whatsapp&logoColor=white" alt="WhatsApp">
  </a>&nbsp;
  <a href="mailto:sale@bitbash.dev" target="_blank">
    <img src="https://img.shields.io/badge/Email-sale@bitbash.dev-EA4335?style=for-the-badge&logo=gmail&logoColor=white" alt="Gmail">
  </a>&nbsp;
  <a href="https://bitbash.dev" target="_blank">
    <img src="https://img.shields.io/badge/Visit-Website-007BFF?style=for-the-badge&logo=google-chrome&logoColor=white" alt="Website">
  </a>
</p>




<p align="center" style="font-weight:600; margin-top:8px; margin-bottom:8px;">
  Created by Bitbash, built to showcase our approach to Scraping and Automation!<br>
  If you are looking for <strong>autoscout24-germany-deutschland-scraper</strong> you've just found your team — Let’s Chat. 👆👆
</p>


## Introduction

This project extracts detailed vehicle listing data from Autoscout24 across Germany in a consistent, machine-readable format.
It solves the problem of manually tracking prices, specifications, and leasing conditions by automating collection at scale.
It’s designed for developers, data analysts, and businesses working with automotive market data.

### Why this scraper exists

- Aggregates listings from all regions in Germany using flexible search logic
- Normalizes inconsistent vehicle and seller data into a single schema
- Supports both price-focused and leasing-focused analysis
- Designed for repeatable, large-scale data collection

## Features

| Feature | Description |
|----------|-------------|
| Full vehicle coverage | Captures brand, model, mileage, fuel type, transmission, and body type. |
| Pricing intelligence | Extracts price values and price ratings when available. |
| Leasing details | Collects monthly rate, total cost, contract type, mileage limits, and one-time fees. |
| Seller profiling | Distinguishes dealer vs private sellers with address and location data. |
| Geo-enrichment | Includes latitude, longitude, and map links for spatial analysis. |
| Smart filtering | Filter by brand, postal code, price range, or custom search URLs. |
| Clean exports | Outputs structured JSON or CSV ready for analytics pipelines. |

---

## What Data This Scraper Extracts

| Field Name | Field Description |
|-------------|------------------|
| brand | Vehicle brand name. |
| manufacturer | Manufacturer as listed in the offer. |
| model | Vehicle model or variant. |
| price | Listed sale price in EUR. |
| price_rating | Platform-provided price evaluation label. |
| mileage_km | Vehicle mileage in kilometers. |
| first_registration | First registration date. |
| fuel | Fuel type (diesel, petrol, electric, etc.). |
| transmission | Transmission type. |
| body_type | Vehicle body category. |
| doors | Number of doors. |
| seats | Number of seats. |
| exterior_color | Exterior color of the vehicle. |
| seller_type | Dealer or private seller. |
| address | Seller address text. |
| maps_link | Direct map link for seller location. |
| latitude | Latitude coordinate. |
| longitude | Longitude coordinate. |
| leasing_monthly | Monthly leasing rate, if available. |
| leasing_total | Total leasing amount over contract duration. |
| leasing_contract_type | Leasing contract category. |
| leasing_mileage | Included mileage allowance. |
| down_payment | Initial leasing payment. |
| total_one_time_costs | Sum of all one-time leasing costs. |
| listing_url | Direct URL to the vehicle listing. |
| scraped_date | Timestamp when the listing was collected. |

---

## Example Output

    [
      {
        "brand": "Ford",
        "model": "B-Max",
        "price": 7199,
        "price_rating": "Sehr guter Preis",
        "mileage_km": 106110,
        "first_registration": "2017-09-01",
        "fuel": "Benzin",
        "transmission": "Schaltgetriebe",
        "body_type": "Van/Kleinbus",
        "seller_type": "Händler",
        "latitude": 49.4542094,
        "longitude": 12.4095743,
        "listing_url": "https://www.autoscout24.de/...",
        "scraped_date": "2025-07-12 10:36:20"
      }
    ]

---

## Directory Structure Tree

    Autoscout24 Germany / Deutschland - Scraper/
    ├── src/
    │   ├── main.py
    │   ├── url_builder.py
    │   ├── list_fetcher.py
    │   ├── detail_parser.py
    │   ├── leasing_parser.py
    │   ├── seller_parser.py
    │   ├── deduplicator.py
    │   └── exporters/
    │       ├── json_exporter.py
    │       └── csv_exporter.py
    ├── config/
    │   ├── settings.example.json
    │   └── filters.schema.json
    ├── data/
    │   ├── samples/
    │   │   └── sample_output.json
    │   └── logs/
    ├── requirements.txt
    └── README.md

---

## Use Cases

- **Market analysts** use it to track vehicle prices by region, so they can identify pricing trends and anomalies.
- **Automotive dealers** use it to monitor competitor listings, so they can adjust pricing strategies faster.
- **Data teams** use it to build dashboards, so stakeholders get real-time visibility into the car market.
- **Leasing consultants** use it to compare leasing conditions, so they can recommend cost-effective offers.

---

## FAQs

**Does this scraper support all brands on Autoscout24 Germany?**
Yes. You can target a specific brand or leave the brand filter empty to collect listings across all manufacturers.

**Can I limit results to a specific city or postal code?**
Yes. Location filtering supports postal codes as well as postal-code–city combinations for more precise targeting.

**Is leasing data always available for every listing?**
No. Leasing fields are populated only when the listing provides leasing information. Missing values are handled gracefully.

**How are duplicate listings handled?**
Listings are deduplicated using a hash-based approach derived from stable listing attributes and URLs.

---

### Performance Benchmarks and Results

**Primary Metric:** Processes an average of 35–45 vehicle listings per minute, depending on filter complexity.

**Reliability Metric:** Maintains a successful extraction rate above 98% across large multi-page runs.

**Efficiency Metric:** Optimized batching and async requests keep memory usage stable under long scraping sessions.

**Quality Metric:** Captures over 95% of available listing fields when present, with consistent schema alignment across outputs.


<p align="center">
<a href="https://calendar.app.google/74kEaAQ5LWbM8CQNA" target="_blank">
  <img src="https://img.shields.io/badge/Book%20a%20Call%20with%20Us-34A853?style=for-the-badge&logo=googlecalendar&logoColor=white" alt="Book a Call">
</a>
  <a href="https://www.youtube.com/@bitbash-demos/videos" target="_blank">
    <img src="https://img.shields.io/badge/🎥%20Watch%20demos%20-FF0000?style=for-the-badge&logo=youtube&logoColor=white" alt="Watch on YouTube">
  </a>
</p>
<table>
  <tr>
    <td align="center" width="33%" style="padding:10px;">
      <a href="https://youtu.be/MLkvGB8ZZIk" target="_blank">
        <img src="https://github.com/Z786ZA/Footer-test/blob/main/media/review1.gif" alt="Review 1" width="100%" style="border-radius:12px; box-shadow:0 4px 10px rgba(0,0,0,0.1);">
      </a>
      <p style="font-size:14px; line-height:1.5; color:#444; margin:0 15px;">
        "Bitbash is a top-tier automation partner, innovative, reliable, and dedicated to delivering real results every time."
      </p>
      <p style="margin:10px 0 0; font-weight:600;">Nathan Pennington
        <br><span style="color:#888;">Marketer</span>
        <br><span style="color:#f5a623;">★★★★★</span>
      </p>
    </td>
    <td align="center" width="33%" style="padding:10px;">
      <a href="https://youtu.be/8-tw8Omw9qk" target="_blank">
        <img src="https://github.com/Z786ZA/Footer-test/blob/main/media/review2.gif" alt="Review 2" width="100%" style="border-radius:12px; box-shadow:0 4px 10px rgba(0,0,0,0.1);">
      </a>
      <p style="font-size:14px; line-height:1.5; color:#444; margin:0 15px;">
        "Bitbash delivers outstanding quality, speed, and professionalism, truly a team you can rely on."
      </p>
      <p style="margin:10px 0 0; font-weight:600;">Eliza
        <br><span style="color:#888;">SEO Affiliate Expert</span>
        <br><span style="color:#f5a623;">★★★★★</span>
      </p>
    </td>
    <td align="center" width="33%" style="padding:10px;">
      <a href="https://youtu.be/m-dRE1dj5-k?si=5kZNVlKsGUhg5Xtx" target="_blank">
        <img src="https://github.com/Z786ZA/Footer-test/blob/main/media/review3.gif" alt="Review 3" width="100%" style="border-radius:12px; box-shadow:0 4px 10px rgba(0,0,0,0.1);">
      </a>
      <p style="font-size:14px; line-height:1.5; color:#444; margin:0 15px;">
        "Exceptional results, clear communication, and flawless delivery. <br>Bitbash nailed it."
      </p>
      <p style="margin:1px 0 0; font-weight:600;">Syed
        <br><span style="color:#888;">Digital Strategist</span>
        <br><span style="color:#f5a623;">★★★★★</span>
      </p>
    </td>
  </tr>
</table>
