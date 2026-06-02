%%{init: {"flowchart": {"curve": "stepAfter"}}}%%
flowchart LR
    %% 左側：記憶體與儲存
    subgraph Left ["Memory & Storage"]
        direction TB
        DDR["DDR3 Memory<br>4GB"]
        eMMC["eMMC Storage<br>16GB"]
    end

    %% 中央最大直立長方形：i.MX6 CPU
    CPU["<b>Freescale<br>i.MX6 QuadCore<br>1GHz<br>MCIMX6Q5EYM10AD</b>"]

    %% 右側：螢幕與 USB 擴展（含 Hub IC）
    subgraph Right ["Display & USB IO"]
        direction TB
        Screen["7 inch Panel<br>LVDS1"]
        
        subgraph USBHubs ["USB 2.0 Expansion"]
            direction TB
            Hub1["USB Hub IC<br>4-Port<br>(e.g. USB2514)"]
            Hub2["USB Hub IC<br>6-Port<br>(e.g. USB2517)"]
            USBPorts["10 x USB 2.0 Ports<br>(Host)"]
        end
    end

    %% 連線（全部水平 → 90度直角）
    %% 左側 → CPU
    DDR -->|DDR3| CPU
    eMMC -->|SDIO / eMMC| CPU

    %% CPU → 右側
    CPU -->|LVDS1| Screen
    CPU -->|USB OTG + Host| Hub1
    CPU -->|USB Host (HSIC)| Hub2

    %% Hub 內部擴展
    Hub1 -->|USB 2.0| USBPorts
    Hub2 -->|USB 2.0| USBPorts

    %% 美化樣式（CPU 最大、最醒目）
    style CPU fill:#a5d6ff, stroke:#0b4d91, stroke-width:40px, color:#000000, font-size:46px, font-weight:bold, rx:30, ry:420
    style Left fill:#e6f0ff, stroke:#1565c0, stroke-width:6px
    style Right fill:#e6f0ff, stroke:#1565c0, stroke-width:6px
    style USBHubs fill:#fff3e0, stroke:#f57c00, stroke-width:4px
    style DDR fill:#ffe0b2, stroke:#ef6c00
    style eMMC fill:#ffe0b2, stroke:#ef6c00
    style Screen fill:#ffe0b2, stroke:#ef6c00
    style Hub1 fill:#ffe0b2, stroke:#ef6c00
    style Hub2 fill:#ffe0b2, stroke:#ef6c00
    style USBPorts fill:#ffe0b2, stroke:#ef6c00
