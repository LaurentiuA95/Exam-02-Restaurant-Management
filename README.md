# Exam 2: County Training Center Canteen

## Story
A county training center is hosting a large public-service workshop, and the canteen must serve staff quickly and correctly during the lunch break. Your code will help the canteen register orders, calculate totals, and prepare meals in the right queue order.

Everything you need is in `main.py`.

## Exam Style
- Time target: 90 to 120 minutes
- Main file: `main.py`
- Focus: object creation, list appending, `isinstance`, loops, FIFO queue logic, simple dictionary updates

## Main Tasks
1. Complete `Order.add_item()` so menu items are stored in the order.
2. Complete `Order.calculate_subtotal()` by summing item prices.
3. Complete `Order.calculate_total()`:
   - meals get a 9% VAT
   - drinks get a 19% VAT
4. Complete `Kitchen.add_order()` so orders join the back of the queue.
5. Complete `Kitchen.prepare_next_order()` so it:
   - removes the oldest order
   - reduces inventory for each ingredient in every meal
   - prints a warning if an ingredient goes below `0`

## What Is Already Given
- The starter classes
- Example menu items
- Example inventory
- A checklist of behaviors to test

## Example Input and Expected Output

**Input (Menu and Inventory):**
- Inventory: `{"tomatoes": 5, "bread": 2}`
- Meal: `Tomato Salad` (Price: `10`, Ingredients: `["tomatoes", "tomatoes"]`)
- Drink: `Water` (Price: `5`, Served Cold: `True`)

**Action:**
```python
order = Order("Table 1")
order.add_item(Meal)
order.add_item(Drink)

kitchen = Kitchen(Inventory)
kitchen.add_order(order)
kitchen.prepare_next_order()
```

**Expected Results:**
- `calculate_subtotal()` should return `15` (10 + 5).
- `calculate_total()` should return `16.85` (10 * 1.09 + 5 * 1.19).
- After `prepare_next_order()`, the kitchen inventory for `"tomatoes"` should be `3` (5 - 2).

## Optional Task
At the bottom of `main.py`, complete `count_item_names(orders)`.

This bonus asks you to build a dictionary that counts how many times each menu item name appears across many orders.

## Run
```bash
python main.py
```
