```mermaid
flowchart LR
    DDR[DDR3 Memory<br>4GB] -->|DDR3| CPU
    eMMC[eMMC Storage<br>16GB] -->|SDIO / eMMC| CPU

    CPU[<b>Freescale i.MX6<br>QuadCore 1GHz<br>MCIMX6Q5EYM10AD</b>]

    CPU -->|LVDS1| Screen
    CPU -->|USB OTG + Host| Hub1
    CPU -->|USB Host (HSIC)| Hub2

    Hub1 -->|USB 2.0 x4| USB
    Hub2 -->|USB 2.0 x6| USB
