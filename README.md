# Automated-Restocking-Optimization-Engine
This project implements an inventory restocking system designed for FMCG (Fast-Moving Consumer Goods) environments. The objective is to determine the optimal reorder quantity that minimizes total inventory cost while preventing stockouts. The project is consistent with the OOP principles.
🚀 Automated FMCG Restocking Optimization Engine

This project simulates an automated restocking engine for an FMCG (Fast-Moving Consumer Goods) inventory system.
It uses Inventory Strategies, Supplier Simulation with Lead Time, Daily Demand Modeling, and Stock Optimization — all written using Object-Oriented Programming and SOLID principles.

The goal is to help warehouses automatically decide how much stock to order and when, reducing costs and avoiding stock-outs.

📊 Key Features
Feature	Description
🔄 Daily Inventory Simulation	Stock decreases due to demand, replenished via supplier orders
📦 Restocking Strategies	EOQ, Heuristic, & Linear Programming (PuLP) strategies implemented
🚚 Realistic Supplier Model	MOQ, supply limits, lead time, fill rate
📁 Warehouse System	Tracks inventory, orders, stock levels, costs
📈 Visualization	Stock levels, cumulative cost, reorder events plotted
🎯 OOP + SOLID Design	Clean modular architecture with extensibility
🧠 Strategies Implemented
Strategy	Method	Use Case
🧮 EOQ Strategy	Economic Order Quantity	Balanced demand-based ordering
⚙️ Heuristic Strategy	Rule-based restocking	Quick decisions without detailed math
📊 LP Strategy (PuLP)	Linear Optimization	Best decision under constraints (budget/storage)

You can switch strategies easily by changing just one line — thanks to the Strategy Pattern.

🧱 Project Architecture
Warehouse
  ├── InventoryItem
  ├── SupplierAgent
  ├── RestockStrategy (Interface)
  │     ├── EOQStrategy
  │     ├── HeuristicStrategy
  │     └── LPStrategy
  └── Simulation & Reports

💡 How the System Works
1️⃣ Initialize items & suppliers

Each product has:

Initial stock

Annual demand (converted to daily demand)

Ordering cost, unit cost, holding cost

Max warehouse capacity

Supplier assigned

2️⃣ Daily Simulation

For each day:

Receive arriving supplier shipments

Random daily demand reduces stock

Strategy decides order quantity

Order placed with supplier (lead-time simulated)

Costs and stock history recorded

3️⃣ Visualization & Summary

✅ Stock level chart
✅ Cost accumulation plot
✅ Demand vs Reorder plot
✅ Final warehouse summary table

🧠 OOP Concepts Used
Concept	Usage
Abstraction	RestockStrategy interface hides strategy implementation
Encapsulation	InventoryItem, SupplierAgent, Warehouse keep their own data & methods
Inheritance	EOQ, LP, Heuristic strategies inherit from RestockStrategy
Polymorphism	strategy.plan() behaves differently depending on strategy class
Composition	Warehouse contains many InventoryItem and SupplierAgent objects
🧱 SOLID Principles Applied
Principle	Implementation
✅ S — Single Responsibility	Each class has one job (supplier controls supply, item tracks stock, etc.)
✅ O — Open/Closed	New strategies can be added without modifying core classes
✅ L — Liskov Substitution	All strategies can replace each other without breaking system
✅ I — Interface Segregation	Strategy interface provides only what is needed (plan())
✅ D — Dependency Inversion	Warehouse depends on abstraction (RestockStrategy) not concrete classes
🛠️ Installation & Setup
Install Dependencies
pip install pulp matplotlib


Note: PuLP is only required if using the LP strategy.

▶️ Run the Simulation
python main.py


By default, EOQ strategy runs.
To switch strategies:

strategy = EOQStrategy()
# strategy = HeuristicStrategy()
# strategy = LPStrategy(budget=50000, additional_storage_capacity=1000, safety_days=5)
