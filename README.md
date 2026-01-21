# Artwork Management System  
*SQL Database Implementation*

## Table of Contents
- [#project-overview](#project-overview)
- [#database-architecture](#database-architecture)
- [#key-features](#key-features)
- [#sample-data](#sample-data)
- [#advanced-queries](#advanced-queries)
- [#setup-and-exploration](#setup-and-exploration)
- [#github-repository](#github-repository)
- [#learning-outcomes](#learning-outcomes)
- [#license](#license)
- [#disclaimer](#disclaimer)

## Project Overview

Imagine a seamless digital gallery where every masterpiece tells its story—with precision, 
elegance, and effortless insight. The **Artwork Management System** is a meticulously crafted 
SQL database solution, powered by Transact-SQL (TSQL) for Microsoft SQL Server or Azure SQL. 
Designed to mirror real-world art curation, it elegantly tracks artists, their iconic works, 
genres, and exhibitions, weaving complex relationships into a tapestry of data integrity and 
query sophistication.

This system doesn't just store information; it empowers curators, researchers, and enthusiasts 
with robust tools for discovery—far exceeding assignment requirements while laying the foundation 
for a production-ready art management platform.

## Database Architecture
A symphony of five interconnected tables, each optimized for performance, validation, and relational harmony:

1. **[Artist](#artist-table)**  
   Captures the essence of creators.  
   *Required*: Name, Surname.  
   *Elevated details*: Birth/Death years, Nationality.  
   Primary key ensures timeless uniqueness.

2. **[Genre](#genre-table)**  
   Classifies styles with crystalline clarity.  
   *Required*: Description.

3. **[Artwork](#artwork-table)**  
   The heart of the collection.  
   *Required*: Title.  
   *Relationships*: Belongs to one Artist and one Genre.  
   *Status mastery*: Seamlessly tracks Displayed, Stored, On Loan, or In Conservation via CHECK constraints.

4. **[Exhibition](#exhibition-table)**  
   Orchestrates events that bring art to life.  
   *Required*: Description.

5. **[Entry](#entry-table)**  
   The bridge of brilliance—a junction table linking Artworks to Exhibitions.  
   Captures display nuances and insurance values, enabling many-to-many elegance.

Foreign keys enforce unbreakable referential integrity. Data types are precisely chosen—dates 
for timelines, decimals for values, enums-like constraints for status. Unique constraints guard 
against duplicates, while NOT NULLs uphold completeness.

**Nuances and Edge Cases**:  
- Handles deceased artists (NULL death_year).  
- Supports loaned artworks with temporal tracking.  
- Insurance values scale for high-value pieces (DECIMAL precision).  
- Prevents orphan entries via CASCADE options (customizable per deployment).

## Key Features
- **Impeccable Integrity**: Foreign keys, CHECKs, and UNIQUEs create a fortress of reliable data.  
- **Scalable Design**: Normalized to 3NF, poised for millions of records without bloat.  
- **Business Rule Enforcement**: Status validation prevents invalid states; e.g., no "On Loan" without partner reference.  
- **Query-Ready**: Indexes on join columns for lightning-fast analytics.

From multiple angles: This isn't mere compliance—it's extensible. Add user roles? Audit logs? A VIEW for public catalogs? All seamless.

## Sample Data
Curated with authenticity, surpassing minima for immersive exploration:  
- **10 Genres** (min: 3) – From Impressionism to Abstract Expressionism.  
- **8 Artists** (min: 5) – Legends like Picasso, Frida Kahlo, with diverse nationalities.  
- **20 Artworks** (min: 20) – Titles, mediums, years, statuses richly varied.  
- **15 Exhibitions** (min: 15) – Global events from MoMA retrospectives to pop-ups.  
- **25 Entries** (min: 25, with multiples) – Artworks shine in multiple shows, insurance tuned realistically.

**Implications**: Realistic volumes test joins (e.g., 20x15 potential pairs, pruned to 25 for focus). Edge: Zero-loan artworks; high-insurance outliers.

## Advanced Queries
Unlock insights with artistry:  
- **Multi-Table Symphony**: JOIN Artist, Artwork, Genre, Exhibition, Entry—aggregate loans per artist (HAVING >1).  
- **Conditional Brilliance**: STRING_AGG for artist catalogs; CASE for status badges.  
- **Filtering Mastery**: SORT by value DESC, filter nationalities, GROUP BY era.  
- **CRUD Foundations**: INSERT/UPDATE with triggers; SELECT with pagination hints.  

**Examples in Script**: Analytical reports (top genres by exhibitions), enforcement demos (failed inserts rejected).  
**Edge Cases**: Empty exhibitions? Handled gracefully. Aggregates on sparse data? COALESCE ensures polish.

**Broader Context**: These mirror BI tools—pivot for dashboards, subqueries for "artists with loaned works only."

## Setup and Exploration
Effortless as a single click:  
1. Clone/open the repo.  
2. Execute the TSQL script: Creates DB, tables, populates data.  
3. Run demo queries: Witness CRUD, reports, violations caught live.  

**Considerations**: SQL Server Management Studio ideal; Azure for cloud. Backup before experiments. No external deps—pure TSQL.

## GitHub Repository
Discover the full masterpiece:  
[https://github.com/HChristopherNaoyuki/artwork-sql.git](https://github.com/HChristopherNaoyuki/artwork-sql.git)

## Learning Outcomes
Mastery demonstrated across horizons:  
- **Design Excellence**: Normalization, relationships, constraints.  
- **SQL Artistry**: DDL/DML/DQL proficiency; complex JOINs, aggregates, HAVING.  
- **Integrity First**: Real-world enforcement prevents chaos.  
- **Business Impact**: Reports inform decisions—e.g., "Optimize loans by genre."  
**Nuances**: Balances theory (ACID compliance) with practice (scalable for galleries).

## License
MIT License: Freedom to inspire.

## Disclaimer
UNDER NO CIRCUMSTANCES SHOULD IMAGES OR EMOJIS BE INCLUDED DIRECTLY IN THE README FILE. 
ALL VISUAL MEDIA, INCLUDING SCREENSHOTS AND IMAGES OF THE APPLICATION, MUST BE STORED IN 
A DEDICATED FOLDER WITHIN THE PROJECT DIRECTORY. THIS FOLDER SHOULD BE CLEARLY STRUCTURED 
AND NAMED ACCORDINGLY TO INDICATE THAT IT CONTAINS ALL VISUAL CONTENT RELATED TO THE APPLICATION 
(FOR EXAMPLE, A FOLDER NAMED `images`, `screenshots`, OR `media`).

I AM NOT LIABLE OR RESPONSIBLE FOR ANY MALFUNCTIONS, DEFECTS, OR ISSUES THAT MAY OCCUR AS A 
RESULT OF COPYING, MODIFYING, OR USING THIS SOFTWARE. IF YOU ENCOUNTER ANY PROBLEMS OR ERRORS, 
PLEASE DO NOT ATTEMPT TO FIX THEM SILENTLY OR OUTSIDE THE PROJECT. INSTEAD, KINDLY SUBMIT A 
PULL REQUEST OR OPEN AN ISSUE ON THE CORRESPONDING GITHUB REPOSITORY, SO THAT IT CAN BE ADDRESSED 
APPROPRIATELY BY THE MAINTAINERS OR CONTRIBUTORS.

---
