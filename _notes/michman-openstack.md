---
---

# Michman и Openstack

- [Michman](https://michman.ispras.ru/ru/)
- [OpenStack](https://www.openstack.org/)

## Где Michman взаимодействует с OpenStack

- Создаёт виртуальные машины в Nova Compute
- Авторизуется через Keystone

```
                                            OpenStack cloud
                                       ┌──────────────────┐
┌────┐    1     ┌──────────┐      2    │  ┌─────────────┐ │
│User│─────────►│Michman   │─────────────►│  Keystone   │ │
└────┘          │API-server│           │  └─────────────┘ │
                └──────────┘           │                  │
                     │ 3               |                  |
                     ▼                 |                  |
                ┌──────────┐     4     │  ┌─────────────┐ │
                │ Michman  │─────────────►│    Nova     │ │
                │ Launcher │           │  └─────────────┘ │
                └──────────┘           └──────────────────┘

```

1. 
