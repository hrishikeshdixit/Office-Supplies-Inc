# Office Supplies Inc. — Enterprise Database Design

![Oracle SQL](https://img.shields.io/badge/Oracle-SQL-red) ![Database](https://img.shields.io/badge/Database-4NF%20Normalised-blue) ![Course](https://img.shields.io/badge/Course-INSY%205335-navy) ![Status](https://img.shields.io/badge/Status-Completed-brightgreen)

## Overview
A complete end-to-end relational database design and implementation project for Office Supplies Inc. (OSI) — a B2B company selling office supplies to institutional buyers. The project covers the full database development lifecycle from requirements analysis and entity modelling through to Oracle SQL implementation and query execution.

## Course
**INSY 5335 — Applied Database Management**
University of Texas at Arlington · Spring 2025

## Business Scenario
Office Supplies Inc. manages sales representatives, customer accounts, delivery trucks, drivers, inventory items, and orders. The goal was to design an information system to manage all operational data efficiently, ensuring data integrity, minimal redundancy, and scalable analytics.

## Project Deliverables

### Part I — Entity & Relationship Modelling
- Identified all business entities involved in OSI operations
- Defined each entity with clear descriptions
- Created a **Relationship Matrix** to map entity relationships
- Wrote formal **Business Rules** for all entity pairs
- Identified **Supertype-Subtype** relationships (e.g. Employee → Driver, Sales Rep)

### Part II — Database Design & Implementation

#### a. ER Diagrams
- **Diagram 1** — All entities and relationships including Many-to-Many (M:M)
- **Diagram 2** — Bridge entities replacing all M:M relationships
- Notation: PowerPoint (to be migrated to Draw.io)

#### b. Relational Schema — 4th Normal Form (4NF)
Designed normalised schema eliminating all partial, transitive, and multi-valued dependencies:
```
CUSTOMER (CUSTOMER_ID, CustomerName, BillingAddress, ContactPerson, Phone)
ORDER (ORDER_ID, customer_id, sales_rep_id, OrderDate, DeliveryAddress)
ORDER_ITEM (ORDER_ID, ITEM_CODE, Quantity)
ITEM (ITEM_CODE, Description, UnitPrice, UnitsAvailable)
EMPLOYEE (SSN, Name, Address, Phone, EmployeeType, Salary)
DRIVER (SSN, DriverLicenseNo, LicenseExpDate)
SALES_REP (SSN, Commission)
TRUCK (VEHICLE_NO, LicensePlate, LicenseExpDate, InspectionExpDate, driver_ssn)
DELIVERY (DELIVERY_ID, order_id, vehicle_no, DeliveryDate)
```

#### c. Data Dictionary
Complete data dictionary specifying attribute names, data types, sizes, constraints, and schema ownership for all tables.

#### d. Oracle SQL Implementation
- Created all tables in Oracle (Omega server)
- Inserted 5–8 rows per table for testing
- Used `DESCRIBE` and `SELECT` commands to document schema and content

#### e. SQL Queries
| # | Query |
|---|-------|
| 1 | List all customer names, addresses, contact persons and phone numbers |
| 2 | Retrieve all information about a specific order as shown on the order form |
| 3 | Find the phone number of the sales rep who took a specific order |
| 4 | List all orders delivered by a specific driver |
| 5 | Calculate total inventory value for items with unit price exceeding $25 |
| 6 | Additional analytical queries |

## Entities
| Entity | Description |
|--------|-------------|
| Customer | Institutional buyers with unique account numbers |
| Order | Sales transactions placed by customers |
| Item | Office supply products with codes and unit prices |
| Employee | All OSI staff (supertype) |
| Driver | Employee subtype with license information |
| Sales Rep | Employee subtype with salary and commission |
| Truck | Delivery vehicles assigned to drivers |
| Delivery | Shipment records linking orders and trucks |

## Tech Stack
| Tool | Usage |
|------|-------|
| Oracle SQL | Database implementation |
| PowerPoint | ER Diagram design |
| Draw.io | ER Diagram (updated version) |
| SQL*Plus / Omega | Query execution & testing |

## Repository Structure
```
├── diagrams/
│   ├── ER_diagram_with_many_to_many.png
│   └── ER_diagram_with_bridge_entities.png
├── sql/
│   ├── create_tables.sql
│   ├── insert_data.sql
│   └── queries.sql
├── docs/
│   ├── data_dictionary.pdf
│   └── relational_schema.pdf
└── README.md
```

## How to Run
1. Clone the repository
```bash
git clone https://github.com/yourusername/office-supplies-database
```
2. Connect to Oracle SQL environment
3. Run table creation script
```sql
@sql/create_tables.sql
```
4. Insert sample data
```sql
@sql/insert_data.sql
```
5. Execute queries
```sql
@sql/queries.sql
```

## Team
Group project — INSY 5335, Spring 2025
**Hrishikesh Umesh Dixit** · MS Information Systems, UTA

## Author
**Hrishikesh Umesh Dixit**
MS Information Systems — University of Texas at Arlington
[LinkedIn](https://linkedin.com/in/hrishikesh-dixit) · [Portfolio](https://yourportfolio.com)
