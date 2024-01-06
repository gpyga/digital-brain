2024-01-06 11:01:84
Status: #reference
Tags: [[Design Principles]]
# Law of Demeter

```ad-quote
Each unit should have only limited knowledge about other units: only units "closely" related to the current unit.

---

Each unit should only talk to its friends; Don't talk to strangers.
```

The law was discovered by [[Ian Holland]].

```ad-note
This essentially means that there should be no hidden dependencies. If $A >> B >> C$, then $C$ should only talk to $A$ with $B$ as a mediator - which is to say, only $B$ can tell $C$ what $A$ has to say.
```

---

## References
[[@LawDemeterGeneral]]