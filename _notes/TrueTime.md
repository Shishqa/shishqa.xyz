---
---

# TrueTime

`TT.Now() -> [from, to]` - настоящее время внутри интервала

- daemons + time masters + armageddon masters
- local
- helps to choose global monotonic timestamps
- `from - to` не слишком большое (`<= 6ms` в рамках ЦОДа)

## Used by Google in

- [Spanner](https://cloud.google.com/spanner)

## See also

- [[GPS]]
