# SDLC, Monolithic Architecture, Microservices, Waterfall, and Agile

### Example: ApnaShop E-Commerce Website

## Overview

This document explains key software development concepts using an e-commerce website (**ApnaShop**) as a real-world example.

---

# 1. Software Development Life Cycle (SDLC)

The **Software Development Life Cycle (SDLC)** is a structured process used to design, develop, test, deploy, and maintain software applications.

## SDLC Phases

### 1. Requirement Gathering

Business stakeholders define the requirements.

**Example (ApnaShop):**

* User Registration & Login
* Product Search
* Shopping Cart
* Online Payments
* Order Tracking
* Admin Dashboard

### 2. Planning

The project team estimates:

* Budget
* Resources
* Timeline
* Technology Stack

### 3. Design

Architects and designers create:

* System Architecture
* Database Design
* User Interface (UI)
* API Specifications

### 4. Development

Developers implement the application features.

### 5. Testing

QA engineers verify:

* Functionality
* Performance
* Security
* Usability

### 6. Deployment

The application is released to production.

### 7. Maintenance

The team fixes bugs, improves performance, and adds new features.

---

# 2. Monolithic Architecture

A **Monolithic Architecture** is a software design where all application components are built and deployed as a single unit.

## ApnaShop Monolithic Structure

```text
ApnaShop Application
│
├── User Module
├── Product Module
├── Cart Module
├── Payment Module
├── Order Module
└── Admin Module
```

## Request Flow

```text
Customer
    │
    ▼
ApnaShop Application
    │
    ▼
Database
```

## Advantages

* Simple to develop initially
* Easy deployment
* Lower infrastructure complexity

## Disadvantages

* Difficult to scale individual components
* Large codebase becomes harder to maintain
* Entire application must be redeployed for small changes

## Example

If the Payment module needs an update, the entire ApnaShop application must be rebuilt and redeployed.

---

# 3. Microservices Architecture

A **Microservices Architecture** divides the application into independent services that communicate through APIs.

## ApnaShop Microservices Structure

```text
┌─────────────────┐
│ User Service    │
└─────────────────┘

┌─────────────────┐
│ Product Service │
└─────────────────┘

┌─────────────────┐
│ Cart Service    │
└─────────────────┘

┌─────────────────┐
│ Payment Service │
└─────────────────┘

┌─────────────────┐
│ Order Service   │
└─────────────────┘

┌─────────────────┐
│ Notification Svc│
└─────────────────┘
```

## Request Flow

```text
Customer
    │
    ▼
API Gateway
    │
    ├── User Service
    ├── Product Service
    ├── Cart Service
    ├── Payment Service
    └── Order Service
```

## Advantages

* Independent deployment
* Better scalability
* Easier maintenance
* Faster development by multiple teams

## Disadvantages

* More complex architecture
* Service communication overhead
* Monitoring and debugging are more challenging

## Example

During a festival sale, only the Product Service can be scaled without increasing resources for the entire application.

---

# 4. Waterfall Model

The **Waterfall Model** is a traditional software development methodology where each phase is completed before the next one begins.

## Process Flow

```text
Requirements
      ↓
Design
      ↓
Development
      ↓
Testing
      ↓
Deployment
```

## ApnaShop Example

| Phase        | Duration  |
| ------------ | --------- |
| Requirements | Month 1   |
| Design       | Month 2   |
| Development  | Month 3-5 |
| Testing      | Month 6   |
| Deployment   | Month 7   |

## Characteristics

* Sequential process
* Documentation-heavy
* Changes are difficult after development begins

## Advantages

* Easy to manage
* Clear milestones
* Suitable for fixed requirements

## Disadvantages

* Limited flexibility
* Late customer feedback
* High cost of changes

## Example

If customers request a Wishlist feature after development is complete, significant rework may be required.

---

# 5. Agile Methodology

**Agile** is an iterative software development methodology where features are delivered in small increments called **Sprints**.

## Agile Sprint Example for ApnaShop

### Sprint 1

* User Registration
* Login Functionality

### Sprint 2

* Product Listing
* Product Search

### Sprint 3

* Shopping Cart

### Sprint 4

* Payment Integration

### Sprint 5

* Order Tracking

## Agile Process

```text
Plan
  ↓
Develop
  ↓
Test
  ↓
Release
  ↓
Feedback
  ↓
Next Sprint
```

## Advantages

* Faster delivery
* Continuous customer feedback
* Easy adaptation to changing requirements
* Reduced project risk

## Disadvantages

* Requires active stakeholder involvement
* Scope changes can occur frequently

## Example

If customers request a Wishlist feature, it can be planned and delivered in the next sprint without affecting the entire project.

---

# Comparison

## Monolithic vs Microservices

| Feature           | Monolithic                | Microservices                 |
| ----------------- | ------------------------- | ----------------------------- |
| Architecture      | Single Application        | Multiple Independent Services |
| Deployment        | Entire Application        | Individual Services           |
| Scalability       | Limited                   | High                          |
| Maintenance       | Difficult as system grows | Easier                        |
| Team Independence | Low                       | High                          |

---

## Waterfall vs Agile

| Feature             | Waterfall      | Agile             |
| ------------------- | -------------- | ----------------- |
| Development Style   | Sequential     | Iterative         |
| Flexibility         | Low            | High              |
| Customer Feedback   | End of Project | Continuous        |
| Requirement Changes | Difficult      | Easy              |
| Delivery Frequency  | One Release    | Multiple Releases |

---

# Conclusion

Using ApnaShop as an example:

* **SDLC** defines the complete software development process.
* **Monolithic Architecture** keeps all functionality within a single application.
* **Microservices Architecture** separates functionality into independent services.
* **Waterfall** follows a sequential development approach.
* **Agile** delivers software incrementally through short development cycles (sprints).

For modern e-commerce platforms like ApnaShop, Agile methodology combined with Microservices Architecture is commonly preferred due to better scalability, flexibility, and faster delivery.
