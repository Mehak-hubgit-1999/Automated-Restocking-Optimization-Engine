# Automated-Restocking-Optimization-Engine
This project implements an inventory restocking system designed for FMCG (Fast-Moving Consumer Goods) environments. The objective is to determine the optimal reorder quantity that minimizes total inventory cost while preventing stockouts. The project is consistent with the OOP principles.

classDiagram

    class Warehouse {
        - inventory: float
        - demand_rate: float
        - holding_cost: float
        - ordering_cost: float
        + update_inventory()
        + simulate_demand()
    }

    class Supplier {
        - name: string
        - lead_time: int
        - reliability: float
        + deliver()
    }

    class InventoryOptimizer {
        - warehouse: Warehouse
        + calculate_eoq()
        + solve_lpp()
        + simulate_lead_time()
    }

    Warehouse --> InventoryOptimizer
    InventoryOptimizer --> Supplier
