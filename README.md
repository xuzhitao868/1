# 1
Here is my control flow:
```mermaid
graph TD
    %% 1. Define Nodes (English Test)
    A(Start);
    B[Set Target Speed (Setpoint)];
    C[Measure Current Speed];
    D{Actual == Target?};
    E{Actual < Target?};
    F[Controller Increase PWM];
    G[Controller Decrease PWM];
    H[Fan Increases Speed];
    I[Fan Decreases Speed];
    J(Airspeed Changes);

    %% 2. Define Links
    A --> B;
    B --> C;
    C --> D;
    D -- Yes --> C;
    D -- No --> E;
    E -- Yes --> F;
    E -- No --> G;
    F --> H;
    G --> I;
    H --> J;
    I --> J;
    J --> C;
