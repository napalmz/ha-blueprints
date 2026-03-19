# ha-blueprints

Collezione di blueprint per automazioni Home Assistant, organizzate per categoria.

## Contenuto del repository

```
.
├── .gitignore
├── LICENSE
├── README.md
└── blueprints
    ├── controllers
    │   ├── ikea-e2489-matter.yaml
    │   └── ikea-e2490-matter.yaml
    ├── generic
    │   └── ikea-klippbok-leak-detector.yaml
    └── hooks
        ├── hook-uhb-cover.yaml
        ├── hook-uhb-light.yaml
        └── hook-uhb-media_player.yaml
```

## Blueprint disponibili

### Controllers

- `blueprints/controllers/ikea-e2489-matter.yaml`  
  🎮 Controller - IKEA BILRESA E2489 Dual Button (Matter · Unified)  
  Gestisce click singolo/doppio e long press/release, con emissione evento `uhb_controller_event`.

- `blueprints/controllers/ikea-e2490-matter.yaml`  
  🎮 Controller - IKEA BILRESA E2490 Scroll Wheel (Matter · Unified)  
  Gestisce canali 1/2/3, click singolo/doppio, long press/release e rotazione rotella, con emissione evento `uhb_controller_event`.

### Hooks

- `blueprints/hooks/hook-uhb-cover.yaml`  
  🪝 Hook - UHB Controller Cover (Matter · Unified)  
  Usa gli eventi `uhb_controller_event` per controllare una cover.

- `blueprints/hooks/hook-uhb-light.yaml`  
  🪝 Hook - UHB Controller Light (Matter · Unified)  
  Usa gli eventi `uhb_controller_event` per controllare una luce con logica avanzata per E2489/E2490.

- `blueprints/hooks/hook-uhb-media_player.yaml`  
  🪝 Hook - UHB Controller Media Player (Matter · Unified)  
  Usa gli eventi `uhb_controller_event` per controllare un media player (play/pause e volume).

### Generic

- `blueprints/generic/ikea-klippbok-leak-detector.yaml`  
  💧 Allerta perdite per sensori selezionati (Matter)  
  Monitora sensori leakage, invia notifiche su bagnato e rientro.
  Include finestra rientro configurabile (1-30 minuti), notifiche mobile opzionali,
  messaggi personalizzabili e azioni personalizzate su bagnato/asciutto.

## Note rapide

- Le blueprint nella cartella `controllers` emettono eventi custom `uhb_controller_event`.
- Le blueprint nella cartella `hooks` consumano gli eventi `uhb_controller_event` per pilotare entità specifiche.
- Le blueprint nella cartella `generic` sono automazioni standalone.
