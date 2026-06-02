```mermaid
flowchart LR
    DDR[DDR3 Memory<br>4GB]
    eMMC[eMMC Storage<br>16GB]
    CPU[Freescale i.MX6<br>QuadCore 1GHz<br>MCIMX6Q5EYM10AD]
    Screen[7 inch Panel<br>LVDS1]
    Hub1[USB Hub IC 4-Port<br>USB2514]
    Hub2[USB Hub IC 6-Port<br>USB2517]
    USB[10 x USB 2.0 Ports]

    DDR -->|DDR3| CPU
    eMMC -->|SDIO / eMMC| CPU
    CPU -->|LVDS1| Screen
    CPU -->|USB OTG + Host| Hub1
    CPU -->|USB Host (HSIC)| Hub2
    Hub1 -->|USB 2.0 x4| USB
    Hub2 -->|USB 2.0 x6| USB
