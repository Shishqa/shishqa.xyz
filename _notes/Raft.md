---
---

# [Raft](https://raft.github.io/)

[[multi-paxos]] with completed inaccuracies

- used widely

## Why better than Paxos?

- decomposed not by *log slots*, but by *phases*
- Paxos is *not convenient*
- **but** Paxos has more degrees of freedom

## Assumptions

- non-Byzantine failures
- messages can be lost or delayed

## The algorithm

__Roles:__ (states of replicas)
1. Leader
2. Follower
3. Candidate

__Terms:__ (may be different on each replica, equivalent to *epochs* in [[multi-paxos]])
1. Election
2. Normal operation under single leader

__Hearbeats:__
- leader _must_ send heartbeats

### 1. Leader election

- Increment current term
- Change state to *candidate*
- Vote for self
- Send `RequestVote` until:
  - receive votes from majority $\rightarrow$ become *leader*
  - receive heartbeat from a valid leader $\rightarrow$ return to *follower*
  - timeout elapses $\rightarrow$ increment term and retry
- Deny vote if log is __more complete:__
  - `self.lastTerm > lastTerm || (self.lastTerm == lastTerm && self.lastIndex > lastIndex)`

### 2. [[replicated-log]] replication

- Send log with heartbeats
- Repair follower logs if follower has something different

## See also

- [LogCabin](https://github.com/logcabin/logcabin) - distributed storage system built on Raft
- [[etcd]]
