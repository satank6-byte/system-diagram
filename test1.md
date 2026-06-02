# i.MX6 系統方塊圖

```mermaid
%%{init: {"flowchart": {"curve": "stepAfter"}}}%%
flowchart LR
    subgraph Left ["External Interfaces"]
        direction TB
        Power["Power Input<br>12~36V"]
        Debug["Debug / UART"]
    end

    CPU["<b>Freescale<br>i.MX6<br>QuadCore 1GHz</b>"]

    subgraph Right ["Storage & Peripherals"]
        direction TB
        DDR["DDR Memory<br>4GB"]
        eMMC["eMMC Storage<br>16GB"]
        Screen["7 inch Panel<br>LVDS / MIPI"]
        USB["USB IO<br>Host / OTG"]
    end

    Power -->|Power| CPU
    Debug -->|UART| CPU

    CPU -->|DDR3| DDR
    CPU -->|SDIO / eMMC| eMMC
    CPU -->|LVDS1| Screen
    CPU -->|USB| USB

    style CPU fill:#a5d6ff, stroke:#0b4d91, stroke-width:40px, color:#000000, font-size:46px, font-weight:bold, rx:30, ry:420
    style Left fill:#e6f0ff, stroke:#1565c0, stroke-width:6px
    style Right fill:#e6f0ff, stroke:#1565c0, stroke-width:6px
