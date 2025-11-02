# Automated-Restocking-Optimization-Engine
This project implements an end-to-end automated FMCG inventory optimization and replenishment engine using a combination of classical Operations Research methods and modern software engineering practices. The system simulates daily demand, tracks warehouse inventory levels, considers supplier behaviour with delivery lead time and reliability constraints, and computes optimal replenishment quantities. It incorporates the Economic Order Quantity (EOQ) model and a Linear Programming (LP)-based optimization strategy to decide order quantities, ensuring a balance between holding cost, ordering cost, and demand fulfilment. A supplier agent class mimics real-world procurement limitations, including minimum/maximum order constraints and probabilistic delivery. The application is built following SOLID object-oriented principles and clean architecture practices, ensuring modularity, extensibility, and clear separation of concerns. Inventory flow is visualized through time-series plots to understand stock dynamics, restocking points, and order fulfilment trends. The project is structured to support CI/CD workflows with testing, linting, and automated build pipelines, making it industry-ready and scalable for further enhancements such as integrating forecasting models, supplier price negotiation logic, or real-time analytics dashboards.

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
