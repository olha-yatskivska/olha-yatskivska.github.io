[Back to Main Page](./)

# Equivalence Partitioning (EP) for Non‑Functional Requirements  


> Purpose: Speed up NFR test design by identifying equivalence partitions and testing only representative conditions.   
> EP for NFRs is about **controlling scope**, not proving perfection.

---

## Do I Need EP Here? 

1. Is the NFR expressed as a range (time, load, size, volume)?

2. Are there multiple values, environments, or conditions?
  
3. Would testing all values be too slow or expensive?

4. Is the system expected to behave the same for a group of conditions?
  


Most ***Yes*** - EP is most valuable when **full coverage is impossible**  

Most ***No*** - EP is weak when **every value behaves differently**

---

## Practical EP Rules

* If it’s a **range → partition it**
* If it’s **special → singleton it**
* If it’s **invalid → isolate it**
* If it’s **risky → sample more**
* If behavior differs → **don’t force EP**

---

## Ready‑to‑Reuse EP Templates per NFR

### Performance (Response Time / Throughput)

System shall respond within `<T>` for up to `<N>` users.

| Parameter | Partition | Representative |
|--------|-----------|----------------|
| Load | Low | 30% of max |
| Load | Typical | 60% of max |
| Load | Max | N |
| Load | Over max | N + x |
| Response time | Valid | ≤ T |
| Response time | Invalid | > T |


---

### Volume / Data Size

System shall process data up to `<SIZE>`.

| Partition | Representative |
|--------|----------------|
| Small | 10–20% of SIZE |
| Typical | 50–70% of SIZE |
| Max | SIZE |
| Over max | SIZE + 1 |
| Singleton | 0 / Empty |

---

### Security (Access Control)

Access is restricted based on user role.


| Partition | Representative |
|--------|----------------|
| Full access | Admin |
| Limited access | User |
| Read‑only | Viewer |
| Invalid | No role / expired token |

---

### Reliability / Stability

System shall operate continuously for `<DURATION>`.


| Partition | Representative |
|--------|----------------|
| Short run | 25% duration |
| Typical run | 50–75% |
| Max run | DURATION |
| Extended run | > DURATION |
| Failure | Restart / crash |

---

### Compatibility / Interoperability

System supports specific platforms.


| Partition | Representative |
|--------|----------------|
| Fully supported | Latest major |
| Supported (older) | N‑1 version |
| Unsupported | Legacy |


---

### Devices / Display

System shall be usable on supported devices.

| Partition | Representative |
|--------|----------------|
| Small | Mobile |
| Medium | Tablet |
| Large | Desktop |
| Invalid | Below min spec |

---

### Localization / i18n

System supports multiple locales.

| Partition | Representative |
|--------|----------------|
| Latin | EN |
| Non‑Latin | JP |
| RTL | AR |
| Unsupported | Invalid locale |

---

## EP + Other Techniques 

| Technique | Why |
|--------|----|
| BVA | Catch edge failures |
| Monitoring | Detect degradation |
| Pairwise | Reduce combinations |
| Soak testing | Long‑term issues |
| Classification Tree | Visualize and reduce combinations  |

---

See also:

* **[Equivalence Partitioning (EP)](./equivalence-partitioning.md)** - Summary of the core concepts from ISTQB Advanced Test Analyst.
* **[Test Matrix for an Input Field](./input-field-test-matrix.md)** - Practical applying EP to an Input Field.
* **[Back to Main Page](./)**
