```mermaid
%%{init: {"flowchart": {"curve": "stepAfter"}}}%%
flowchart LR
    DDR[DDR3 Memory 4GB]
    eMMC[eMMC Storage 16GB]
    CPU[Freescale i.MX6<br>QuadCore 1GHz<br>MCIMX6Q5EYM10AD]
    Screen[7 inch Panel<br>LVDS1]
    Hub1[USB Hub 4-Port<br>USB2514]
    Hub2[USB Hub 6-Port<br>USB2517]
    USB[10 x USB 2.0 Ports]

    DDR -->|DDR3| CPU
    eMMC -->|SDIO| CPU
    CPU -->|LVDS1| Screen
    CPU -->|USB OTG + Host| Hub1
    CPU -->|USB Host HSIC| Hub2
    Hub1 -->|4 ports| USB
    Hub2 -->|6 ports| USB
