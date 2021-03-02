## Hazelcast 3.12.12 eviction comparison

Companion project to https://github.com/LarsKrogJensen/hz4-idle-evict-repro to illustrated that hazelcast 3.12.12 does not show same issue         


### Scenario
Same scenario, here the  

#### Output

Notice the jumps in the stats (users, sessions) while entries are very, very slowly being evicted.

```
11:32:58.795 [main] INFO  com.hazelcast.core.LifecycleService - [10.192.35.218]:5701 [hz3-repro] [3.12.12] [10.192.35.218]:5701 is STARTED
11:32:58.817 [main] INFO  c.h.i.p.impl.PartitionStateManager - [10.192.35.218]:5701 [hz3-repro] [3.12.12] Initializing cluster partition table arrangement...
11:32:59.223 [main] INFO  Main - Added 5000 sessions
11:32:59.224 [main] INFO  Main - Watching stats every 3 seconds, expects that entries starts to expiry after 30 seconds
Main - Repo stats, size: 5000 sessions: 5000 users: 1000
Main - Repo stats, size: 5000 sessions: 5000 users: 1000
Main - Repo stats, size: 5000 sessions: 5000 users: 1000
Main - Repo stats, size: 5000 sessions: 5000 users: 1000
Main - Repo stats, size: 5000 sessions: 5000 users: 1000
Main - Repo stats, size: 5000 sessions: 5000 users: 1000
Main - Repo stats, size: 5000 sessions: 5000 users: 1000
Main - Repo stats, size: 5000 sessions: 5000 users: 1000
Main - Repo stats, size: 5000 sessions: 5000 users: 1000
Main - Repo stats, size: 5000 sessions: 5000 users: 1000
Main - Repo stats, size: 5000 sessions: 5000 users: 1000
Main - Repo stats, size: 5000 sessions: 5000 users: 1000
Main - Repo stats, size: 5000 sessions: 5000 users: 1000
Main - Repo stats, size: 5000 sessions: 5000 users: 1000
Main - Repo stats, size: 5000 sessions: 5000 users: 1000
Main - Repo stats, size: 5000 sessions: 5000 users: 1000
Main - Repo stats, size: 5000 sessions: 5000 users: 1000
Main - Repo stats, size: 5000 sessions: 5000 users: 1000
Main - Repo stats, size: 5000 sessions: 5000 users: 1000
Main - Repo stats, size: 4985 sessions: 0 users: 0        <-- evictions starts
Main - Repo stats, size: 4985 sessions: 0 users: 0            no 'jumps'
Main - Repo stats, size: 4486 sessions: 0 users: 0
Main - Repo stats, size: 4486 sessions: 0 users: 0
Main - Repo stats, size: 3952 sessions: 0 users: 0
Main - Repo stats, size: 3489 sessions: 0 users: 0
Main - Repo stats, size: 3489 sessions: 0 users: 0
Main - Repo stats, size: 3004 sessions: 0 users: 0
Main - Repo stats, size: 3004 sessions: 0 users: 0
Main - Repo stats, size: 2513 sessions: 0 users: 0
Main - Repo stats, size: 2029 sessions: 0 users: 0
Main - Repo stats, size: 2029 sessions: 0 users: 0
Main - Repo stats, size: 1536 sessions: 0 users: 0
Main - Repo stats, size: 1536 sessions: 0 users: 0
Main - Repo stats, size: 1028 sessions: 0 users: 0
Main - Repo stats, size: 526 sessions: 0 users: 0
Main - Repo stats, size: 526 sessions: 0 users: 0
Main - Repo stats, size: 18 sessions: 0 users: 0
Main - Repo stats, size: 18 sessions: 0 users: 0
Main - Repo stats, size: 0 sessions: 0 users: 0
Main - Repo stats, size: 0 sessions: 0 users: 0
```
         
entries evicted promptly