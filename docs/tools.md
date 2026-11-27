# Restow tool reference

Restow offers 16 read tools and five write tools. A workspace administrator signs in and authorizes Claude to access one Restow workspace. Read-only is the default. Write tools appear when the administrator explicitly grants **Read and write**. Restow also checks the connected user's workspace role on each request.

Customer and supplier records, product sales history, and reports require an admin. Product catalog, sales order, and purchase order lookups require an admin or assistant. Inventory lookup is available to all signed-in workspace roles.

## Search

| Tool | What it does |
| --- | --- |
| `search` | Searches across workspace records, including products, customers, orders, purchase orders, and quotes. Non-admin roles get inventory results only. |

## Customers and suppliers

Restow stores buyers and suppliers as customer records.

| Tool | What it does |
| --- | --- |
| `list_customers` | Lists customers and suppliers, with an optional name filter. |
| `get_customer` | Returns one customer or supplier by its Restow record ID. |
| `create_customer` | Creates a customer or supplier. Requires a name and accepts address, city, state, ZIP or postal code, country, email, phone, fax, and description. Admin only. |
| `update_customer` | Edits the supplied fields on an existing customer or supplier. Admin only. |

## Products

| Tool | What it does |
| --- | --- |
| `list_products` | Lists products with stock on hand and stock status. Filters by text or status (low, healthy, out) and sorts by name, part number, manufacturer, stock on hand, minimum quantity, or creation date. |
| `get_product` | Returns one product with stock on hand, number of locations, minimum quantity, and stock status. |
| `get_product_sales` | Returns the product's sales line items with customer, quantity, and price, newest first. Admin only. |
| `create_product` | Creates a catalog product with zero stock. Requires a name and accepts part number, manufacturer, minimum quantity, description, and notes. Admin or assistant. |
| `update_product` | Edits the supplied catalog fields. Stock quantity is separate from these fields. Admin only. |

## Inventory

| Tool | What it does |
| --- | --- |
| `list_inventory` | Lists stock lots, each representing one product at one location. Filters by product, location, product stock status, or lot quantity (positive, zero, or all). Sorts by product, location, quantity, or update time. |

## Sales orders

| Tool | What it does |
| --- | --- |
| `list_orders` | Lists sales orders with customer, totals, paid flag, and fulfillment status (created, packed, or shipped). Filters by customer or status and searches by order number, customer PO reference, or customer name. |
| `get_order` | Returns one sales order with its line items and boxes. |
| `list_unpaid_orders` | Lists orders awaiting payment, with due dates based on payment terms. |
| `list_overdue_orders` | Lists unpaid orders past their due date. |

## Purchase orders

| Tool | What it does |
| --- | --- |
| `list_purchase_orders` | Lists supplier purchase orders and their status (created, arrived, or stored). Filters by supplier or status and searches by purchase order number, supplier reference, or supplier name. |
| `get_purchase_order` | Returns one purchase order with line items and received quantities split into good and bad units. |

For both types of orders, show the order's workspace document number in answers. Use the record ID when a tool requires it.

## Reports

Report dates default to the start of the fiscal year through today and allow a range of up to 366 days.

| Tool | What it does |
| --- | --- |
| `sales_overview` | Returns order count and sales total for the date range, plus current catalog, stock unit, low-stock, and out-of-stock counts. |
| `sales_by_customer` | Ranks up to 50 customers by sales total for the date range. |
| `top_products` | Ranks up to 50 products by sales total, with units sold and order counts. |

## Comments

| Tool | What it does |
| --- | --- |
| `add_comment` | Adds a comment under the connected user's name to a customer, sales order, product, or purchase order. Admin or assistant. |

## Actions available in Restow

Use the Restow app to create or edit sales orders and purchase orders, change their status, mark orders paid, adjust or move inventory, work with quotes, or delete records. Claude can find quotes in search results. The connector has no tool to open a quote.
