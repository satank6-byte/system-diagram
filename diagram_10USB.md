%%{init: {"flowchart": {"curve": "stepAfter"}}}%%
flowchart LR
    %% 左側
    subgraph Left ["Memory & Storage"]
        direction TB
        DDR[DDR3 Memory 4GB]
        eMMC[eMMC Storage 16GB]
    end

    %% 中央最大 CPU
    CPU[Freescale i.MX6<br>QuadCore 1GHz<br>MCIMX6Q5EYM10AD]

    %% 右側
    subgraph Right ["Display & USB IO"]
        direction TB
        Screen[7 inch Panel<br>LVDS1]
        Hub1[USB Hub IC<br>4-Port USB2514]
        Hub2[USB Hub IC<br>6-Port USB2517]
        USB[10 x USB 2.0 Ports]
    end

    %% 連線（強制正交）
    DDR -->|DDR3| CPU
    eMMC -->|SDIO| CPU
    CPU -->|LVDS1| Screen
    CPU -->|USB OTG + Host| Hub1
    CPU -->|USB Host HSIC| Hub2
    Hub1 -->|USB 2.0 x4| USB
    Hub2 -->|USB 2.0 x6| USB

    %% 美化（CPU 最大）
    style CPU fill:#a5d6ff, stroke:#0b4d91, stroke-width:40px, color:#000000, font-size:46px, font-weight:bold, rx:30, ry:420
    style Left fill:#e6f0ff, stroke:#1565c0, stroke-width:6px
    style Right fill:#e6f0ff, stroke:#1565c0, stroke-width:6px```mermaid
flowchart LR
    DDR[DDR3 Memory 4GB]
    eMMC[eMMC Storage 16GB]
    CPU[Freescale i.MX6 QuadCore 1GHz]
    Screen[7 inch Panel LVDS1]
    Hub1[USB Hub 4-Port USB2514]
    Hub2[USB Hub 6-Port USB2517]
    USB[10 x USB 2.0 Ports]

    DDR -->|DDR3| CPU
    eMMC -->|SDIO| CPU
    CPU -->|LVDS1| Screen
    CPU -->|USB OTG + Host| Hub1
    CPU -->|USB Host HSIC| Hub2
    Hub1 -->|4 ports| USB
    Hub2 -->|6 ports| USB
