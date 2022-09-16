# Glue Pizza Store API

## Overview

Your goal is to develop a RESTful API that exposes endpoints which let clients manage a pizza store using .NET Core. Each endpoint should provide CRUD operations. Don't spend more than a few hours on the project. We are looking for a strong understanding of the key concepts, not a perfect implementation.

You should clone this repository and when you're ready to share your work, push it to private repository and our recruitment team will let you know the username to add as a collaborator so we can check it out.

## Technical requirements

> In order to be able to complete this challenge, you should be familiar with .NET Core, RESTful APIs and SQL Server.

- You must use .NET Core and C#.
- The API should be a ASP.NET Core project.
- The API should consume and return data as JSON.
- Data access should be handled by EntityFrameworkCore.
- All data needs to be persisted in a database.
- You can use any NuGet package, but be prepared to justify its usage.
- The solution must be at least linearly scalable.

## API Specification

### Pizza Sizes

| Field | Type |
|---|---|
| id | `int` |
| name | `string` |
| price | `float` |
| toppings | `array` |

```bash
GET /api/sizes # Get all
GET /api/sizes/{id} # Get by id

POST /api/sizes # Create entity
PUT /api/sizes/{id} # Update entity by id

DELETE /api/sizes/{id} # Delete entity
DELETE /api/sizes # Bulk delete
```

### Toppings

| Field | Type |
|---|---|
| id | `int` |
| name | `string` |
| price | `float` |

```bash
GET /api/toppings # Get all
GET /api/toppings/{id} # Get by id

POST /api/toppings # Create entity
PUT /api/toppings/{id} # Update entity by id

DELETE /api/toppings/{id} # Delete entity
DELETE /api/toppings # Bulk delete
```

### Categories

| Field | Type |
|---|---|
| id | `int` |
| name | `string` |
| toppings | `array` |

```bash
GET /api/categories # Get all
GET /api/categories/{id} # Get by id
GET /api/categories/{id}/toppings # Get all toppings for a single category

POST /api/categories # Create entity
PUT /api/categories/{id} # Update entity by id

DELETE /api/categories/{id} # Delete entity
DELETE /api/categories # Bulk delete
DELETE /api/categories/{id}/toppings/{id} # Delete topping from category by id
```

### Orders

| Field | Type |
|---|---|
| id | `int` |
| createdAt | `datetime` |
| items | `array` |

```bash
GET /api/orders # Get all
GET /api/orders/{id} # Get by id

POST /api/orders # Create entity
PUT /api/orders/{id} # Update entity by id

DELETE /api/orders/{id} # Delete entity
DELETE /api/orders # Bulk delete
```

> **General Specifications for each endpoint**
> * GET endpoints should have pagination and able to be sorted by field
> * Deleting a `category` should delete all related `toppings`
> * Deleting an `order` shouldn't affect any other entity
> * Deleting a `pizza size` shouldn't affect `toppings`
> * Endpoints should have Basic Auth
> * Be mindful of correct HTTP status code usage

## Evaluating your work

We are looking production quality code which utilises design patterns where appropriate and conforms to best practices and principles such as SOLID, etc. Feel free to host your project where you feel comfortable, so we are able to make requests and test the final product.

If you're not able to host your app to be access publicly, include enough instructions on how to install and run your app locally.

If you have further questions about the challenge, feel free to reach out. No hard deadlines and no pressure.
