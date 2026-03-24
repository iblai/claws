# Data Sources

Systems and platforms commonly accessed for small business inventory management.

## POS & Inventory Systems

- **Square for Retail** -- POS with inventory management
  - **Items**: item_name, SKU, barcode, category, price, cost, current_stock, reorder_point, vendor
  - **Stock adjustments**: adjustment_type (received/sold/damaged/returned/transfer), quantity, date, reason
  - **Sales data**: items_sold, revenue_by_item, units_per_transaction, refunds, discounts_applied

- **Shopify** -- e-commerce and retail inventory
  - **Products**: title, SKU, barcode, price, compare_at_price, cost, inventory_quantity, variant, vendor, tags
  - **Inventory levels**: location, available, committed, incoming, on_hand
  - **Orders**: order_number, items, quantities, fulfillment_status, tracking_number, customer

- **Lightspeed Retail** -- retail POS and inventory
  - **Items**: description, SKU, UPC, category, brand, cost, retail_price, quantity_on_hand, reorder_point
  - **Purchase orders**: vendor, items_ordered, quantities, costs, status, expected_delivery, received_date
  - **Reports**: inventory_valuation, sell_through_rate, top_sellers, dead_stock, margin_by_category

- **QuickBooks Commerce (formerly TradeGecko)** -- inventory and order management
  - **Products**: name, SKU, variant, cost, price, stock_on_hand, committed_stock, available_stock
  - **Purchase orders**: supplier, items, status (draft/ordered/received/partial), delivery_date
  - **Stock transfers**: from_location, to_location, items, quantities, status

## Supplier & Procurement

- **Direct supplier portals** -- vendor ordering systems
  - **Catalog**: product_name, wholesale_price, MOQ (minimum_order_quantity), lead_time, case_pack_size
  - **Orders**: PO_number, items, quantities, unit_cost, total, status, ship_date, tracking
  - **Invoices**: invoice_number, amount, payment_terms, due_date, credits/returns

## E-commerce Marketplaces

- **Amazon Seller Central** -- marketplace selling
  - **Inventory**: ASIN, SKU, fulfillment_channel (FBA/FBM), quantity_available, inbound_quantity
  - **Sales**: units_sold, revenue, fees (referral/FBA/storage), net_proceeds, buy_box_percentage

- **Etsy** -- handmade/vintage marketplace
  - **Listings**: title, quantity, price, shipping_cost, views, favorites, renewal_date
  - **Sales**: order_number, items, quantity, revenue, fees, shipping_label_cost
