# Artwork Management System  

## Table of Contents

- [Project Overview](#project-overview)
- [Database Architecture](#database-architecture)
- [Key Features](#key-features)
- [Sample Data](#sample-data)
- [Advanced Queries](#advanced-queries)
- [Setup and Exploration](#setup-and-exploration)
- [GitHub Repository](#github-repository)
- [Learning Outcomes](#learning-outcomes)
- [License](#license)
- [Disclaimer](#disclaimer)

## Project Overview

The Artwork Management System is a professional SQL database solution built
with Transact-SQL for Microsoft SQL Server or Azure SQL. It manages artists,
artworks, genres, and exhibitions with precision and data integrity. The
system supports real-world art curation workflows by linking masterpieces to
their creators and show events. It serves curators, researchers, and gallery
managers who need reliable access to collection insights. This implementation
goes beyond basic assignments to deliver a production-ready foundation for
digital art management platforms.

## Database Architecture

The architecture consists of five normalized tables that work together to
maintain relational harmony and enforce business rules. Each table serves a
specific purpose within the overall schema.

1. Artist Table: Stores creator details including name, surname, birth year,
death year, and nationality. The primary key ensures unique identification.

2. Genre Table: Classifies artistic styles using a description field.

3. Artwork Table: Contains the core collection data with title, artist
reference, genre reference, creation year, medium, status, and insurance
value. Status is validated using a CHECK constraint for values such as
Displayed, Stored, On Loan, or In Conservation.

4. Exhibition Table: Manages event information including description, start
date, end date, and location.

5. Entry Table: Serves as a junction linking artworks to exhibitions. It
captures display details and insurance values for each showing.

Foreign keys enforce referential integrity across all relationships. The
design handles edge cases such as deceased artists, loaned artworks, and
high-value insurance figures.

## Key Features

The system provides multiple layers of data protection and performance
optimization. Foreign key constraints prevent orphaned records and maintain
consistency across all tables. CHECK constraints validate status values
and date ranges at the database level. Unique constraints eliminate
duplicate entries while NOT NULL requirements ensure completeness of
critical fields.

Scalability is achieved through normalization to the third normal form.
Indexes on join columns accelerate query execution for large datasets.
The design supports future extensions such as user role management,
audit logging, and public catalog views without requiring structural
overhauls.

## Sample Data

The database includes carefully curated sample data for meaningful
exploration and testing. The dataset contains ten distinct genres,
covering periods from Impressionism to Abstract Expressionism. Eight
artists represent diverse nationalities and historical periods,
including Picasso and Frida Kahlo.

Twenty artworks provide a rich mix of titles, mediums, creation years,
and status values. Fifteen exhibitions simulate global events ranging
from major museum retrospectives to smaller gallery pop-ups. Twenty-
five entry records link artworks to multiple exhibitions with realistic
insurance valuations.

This volume of data supports meaningful joins and aggregate queries
while maintaining fast execution for learning purposes. Edge cases
such as artworks that never go on loan and outliers with high insurance
values are included for comprehensive testing.

## Advanced Queries

The system supports sophisticated analytical queries that mirror real-
world business intelligence needs. Multi-table joins combine artist,
artwork, genre, exhibition, and entry data to produce comprehensive
reports. Conditional aggregation using functions such as STRING_AGG
creates comma-separated catalogs of artwork per artist.

The CASE statement enables status badges and custom categorization.
Filtering capabilities include sorting by insurance value, filtering by
nationality, and grouping artistic works by historical era. The script
also demonstrates CRUD operations with INSERT, UPDATE, and SELECT
statements that include pagination hints for large result sets.

Analytical reports in the script include identifying top genres by
exhibition count and listing artists with multiple loaned works. Empty
exhibitions are handled gracefully, and COALESCE ensures polished
output for sparse data.

## Setup and Exploration

Setting up the database requires minimal steps and no external
dependencies beyond Microsoft SQL Server or Azure SQL. Begin by
cloning the repository or downloading the script file. Open the TSQL
script in SQL Server Management Studio or your preferred editor.
Execute the entire script to create the database, all tables,
relationships, and sample data in one operation.

After successful execution, run the demo queries section to see CRUD
operations in action and observe constraint violations being caught
by the system. For cloud deployment, Azure SQL Database supports the
same script without modifications. Always back up your database
before running experimental modifications.

## GitHub Repository

Access the complete project repository for the latest version,
documentation, and support:

```
https://github.com/HChristopherNaoyuki/artwork-sql.git
```

Use the following command to clone the repository to your local
machine:

```
git clone https://github.com/HChristopherNaoyuki/artwork-sql.git
```

## Learning Outcomes

This project demonstrates mastery of multiple database design and
SQL proficiency areas. Design excellence is shown through proper
normalization, relationship mapping, and constraint implementation.
SQL artistry appears in DDL, DML, and DQL statements featuring
complex joins, aggregate functions, and the HAVING clause.

Integrity enforcement is demonstrated through real-world prevention
of invalid data states. Business impact is visible in reports that
support operational decisions such as optimizing loan strategies by
genre. The solution balances theoretical ACID compliance with
practical scalability for gallery environments.

## License

MIT License. You are free to use, modify, and distribute this
software for any purpose, subject to the terms of the MIT License.

## Disclaimer

Under no circumstances should images or emojis be included directly
in the readme file. All visual media, including screenshots and images
of the application, must be stored in a dedicated folder within the
project directory. This folder should be clearly structured and named
accordingly to indicate that it contains all visual content related
to the application (for example, a folder named images, screenshots,
or media).

I am not liable or responsible for any malfunctions, defects, or
issues that may occur as a result of copying, modifying, or using
this software. If you encounter any problems or errors, please do
not attempt to fix them silently or outside the project. Instead,
kindly submit a pull request or open an issue on the corresponding
GitHub repository, so that it can be addressed appropriately by the
maintainers or contributors.


---

End of Document

---
