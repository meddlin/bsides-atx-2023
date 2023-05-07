# DiscoveraBLE: bluetooth low energy (BLE) tech basics and engagement

Spaker: Pearce Barry


## BLE Brief

- wireless
- low cost, low power
- public specification (3100 pages, though)
- in a lot of stuff though
    - fitbit, air tags/tile, smartphones


## Brief history of BLE

- started ~1989 at Ericsson, they needed some headsets
- then the BT special interest group was started

- BLE -> bluetooth low end extension, then became bluetooth low energy
- the name "Wibree" was in here somewhere
- then this was BT5


## BLE info

- 2.4GHz
- uses frequency hopping
- other nearby frequency interference can be problematic for this
- but also, if the hopping sequence isn't known it couldn't prevent other things from picking up BLE
- Range: 400m (at the top end)
- Throughput: 125Kbps, 500Kbps, 1Mbps, 2Mbps
- fast connections: a few ms (original BT was more like seconds)
- can sleep between connections
- useful for beacon type advertising
- supports mesh networking
- widely supported


## Uses

- consumer devices
- asset/person tracking
- environmental monitoring
- target advertising


## How it works

- [insert pic]

- advertising
- pairing
- bonding (not a requirement for BLE, but is how devices remember each other)
- profiles
    - GATT, ATT
- related: BTHome project


## Discover, Interact with BLE

- nRF Connect mobile app: Android, iOS, desktop app
- nRF Logger is worth looking at too
- nRF Edge Impulse
- [insert pic]

- you can also have nRF Connect clone BLE advertising packets


## Vulns

- AttackerKB, search for "bluetooth low energy"
- look at stories around:
    - "Tapplock"
    - Winco Fireworks Firefly
    - Xiaomi scooters
    - Swell kit mod (vaping devices) - "vapbomb" exploit
    - Mimo Baby 2 (baby monitor)
    - tvOS 16.4
    - SOOIL Developments Co. Ltd
    - Silicon Labs Bluetooth low energy SDK

- Sweyntooth
    - look for this project