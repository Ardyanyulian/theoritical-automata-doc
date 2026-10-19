# BAB 2

---

## 1. Formalitas Mesin DFA

Sebuah mesin **Deterministic Finite Automata (DFA)** didefinisikan secara matematis sebagai 5-tuple:

$$M = (Q, \Sigma, \delta, q_0, F)$$

### Komponen Mesin
* **$Q$** : Himpunan berhingga *state* / status (contoh: $Q = \{q_0, q_1, q_2\}$).
* **$\Sigma$** : Himpunan simbol input / alfabet (contoh: $\Sigma = \{0, 1\}$).
* **$\delta$** : Fungsi transisi, yaitu pemetaan pemindahan state:
  $$\delta : Q \times \Sigma \rightarrow Q$$
* **$q_0$** : *Start state* / status awal ($q_0 \in Q$).
* **$F$** : Himpunan *final state* / status akhir ($F \subseteq Q$).

---

## 2. Contoh Kasus Mesin Contoh $M$

### A. Komponen Mesin $M$
* $Q = \{q_0, q_1, q_2\}$
* $\Sigma = \{0, 1\}$
* $q_0 = q_0$
* $F = \{q_1\}$ *(ditandai dengan lingkaran ganda pada diagram)*

### B. Tabel / Fungsi Transisi ($\delta$)
* $\delta(q_0, 0) = q_0$
* $\delta(q_0, 1) = q_1$
* $\delta(q_1, 0) = q_0$
* $\delta(q_1, 1) = q_2$
* $\delta(q_2, 0) = q_0$
* $\delta(q_2, 1) = q_2$

### C. Diagram Transisi
```text
         0                       0
       ┌───┐                   ┌───┐
       ▼   │                   ▼   │
     ┌───────┐        1      ╔═══════╗        1      ┌───────┐
─►───│  q0   │ ────────────► │ ((q1))│ ────────────► │  q2   │
     └───────┘               ╚═══════╝               └───────┘
         ▲                       │                       │
         └───────────────────────┴───────────────────────┘
                     0

```

### D. Pengujian String (Diterima / Ditolak)

Suatu string $S$ **diterima** jika penelusuran transisi berakhir di status akhir ($q \in F$).

#### 1. String $S_1 = 001$

* $\delta(q_0, 0) \rightarrow q_0$
* $\delta(q_0, 0) \rightarrow q_0$
* $\delta(q_0, 1) \rightarrow q_1$
* **Status Akhir:** $q_1 \in F \implies$ **DITERIMA**

#### 2. String $S_2 = 0101$

* $\delta(q_0, 0) \rightarrow q_0$
* $\delta(q_0, 1) \rightarrow q_1$
* $\delta(q_1, 0) \rightarrow q_0$
* $\delta(q_0, 1) \rightarrow q_1$
* **Status Akhir:** $q_1 \in F \implies$ **DITERIMA**

---

## 3. Latihan Rancangan DFA ($\Sigma = \{0, 1\}$)

---

### a) Panjang String = 3

* **Komponen Mesin $M$:**
* $Q = \{q_0, q_1, q_2, q_3, q_4\}$
* $\Sigma = \{0, 1\}$
* $q_0 = q_0$
* $F = \{q_3\}$


* **Fungsi Transisi ($\delta$):**
* $\delta(q_0, 0) = q_1, \quad \delta(q_0, 1) = q_1$
* $\delta(q_1, 0) = q_2, \quad \delta(q_1, 1) = q_2$
* $\delta(q_2, 0) = q_3, \quad \delta(q_2, 1) = q_3$
* $\delta(q_3, 0) = q_4, \quad \delta(q_3, 1) = q_4$
* $\delta(q_4, 0) = q_4, \quad \delta(q_4, 1) = q_4$


* **Diagram Transisi:**

```text

       
            0 1      v        0, 1                0, 1
   ┌───────┐   |   ┌───────┐   │   ┌───────┐   │   ╔═══════╗  0, 1  ┌───────┐
─► │  q0   │ ──-─► │  q1   │ ──┴─► │  q2   │ ──┴─► │ ((q3))│ ─────► │  q4   │
   └───────┘       └───────┘       └───────┘       ╚═══════╝        └───────┘
                                                                      ▲   │
                                                                      └───┘
                                                                      0, 1

```

* **Pengujian String:**
* **Tes $S = 00$ (Panjang 2):**

$$\delta(q_0, 0) \rightarrow q_1 \rightarrow \delta(q_1, 0) \rightarrow q_2$$



*Status akhir:* $q_2 \notin F \implies$ **DITOLAK**
* **Tes $S = 000$ (Panjang 3):**

$$\delta(q_0, 0) \rightarrow q_1 \rightarrow \delta(q_1, 0) \rightarrow q_2 \rightarrow \delta(q_2, 0) \rightarrow q_3$$



*Status akhir:* $q_3 \in F \implies$ **DITERIMA**



---

### b) Panjang String Genap (misal: `00`, `01`, `0101`)

* **Komponen Mesin $M$:**
* $Q = \{q_0, q_1\}$
* $\Sigma = \{0, 1\}$
* $q_0 = q_0$
* $F = \{q_0\}$


* **Fungsi Transisi ($\delta$):**
* $\delta(q_0, 0) = q_1, \quad \delta(q_0, 1) = q_1$
* $\delta(q_1, 0) = q_0, \quad \delta(q_1, 1) = q_0$


* **Diagram Transisi:**

```text
               0, 1
           ┌──────────►
        ╔═══════╗    ┌───────┐
─►──────║ ((q0))║    │  q1   │
        ╚═══════╝    └───────┘
           ◄──────────┘
               0, 1

```

---

### c) Diawali Angka `0` (misal: `01`, `010`, ...)

* **Komponen Mesin $M$:**
* $Q = \{q_0, q_1, q_2\}$
* $\Sigma = \{0, 1\}$
* $q_0 = q_0$
* $F = \{q_1\}$


* **Fungsi Transisi ($\delta$):**
* $\delta(q_0, 0) = q_1$
* $\delta(q_0, 1) = q_2$
* $\delta(q_1, 0) = q_1, \quad \delta(q_1, 1) = q_1$
* $\delta(q_2, 0) = q_2, \quad \delta(q_2, 1) = q_2$


* **Diagram Transisi:**

```text
               0, 1
               ┌───┐
               ▼   │
             ╔═══════╗
       ┌─0─► │ ((q1))│  (Diterima)
       │     ╚═══════╝
   ┌───────┐
─► │  q0   │
   └───────┘
       │     ┌───────┐
       └─1─► │  q2   │  (Trap / Ditolak)
             └───────┘
               ▲   │
               └───┘
               0, 1

```

---

### d) Diakhiri Angka `1` (misal: `1`, `11`, `0111`, ...)

* **Komponen Mesin $M$:**
* $Q = \{q_0, q_1\}$
* $\Sigma = \{0, 1\}$
* $q_0 = q_0$
* $F = \{q_1\}$


* **Fungsi Transisi ($\delta$):**
* $\delta(q_0, 0) = q_0$
* $\delta(q_0, 1) = q_1$
* $\delta(q_1, 0) = q_0$
* $\delta(q_1, 1) = q_1$


* **Diagram Transisi:**

```text
               0                                    1
             ┌───┐                                ┌───┐
             ▼   │                                ▼   │
           ┌───────┐               1            ╔═══════╗
     ─►───│  q0   │ ─────────────────────────► │ ((q1))│
           └───────┘                            ╚═══════╝
               ▲                                    │
               └────────────────────────────────────┘
                                  0

```

* **Pengujian String $S = 01001$:**
* $\delta(q_0, 0) \rightarrow q_0$
* $\delta(q_0, 1) \rightarrow q_1$
* $\delta(q_1, 0) \rightarrow q_0$
* $\delta(q_0, 0) \rightarrow q_0$
* $\delta(q_0, 1) \rightarrow q_1$
* **Status Akhir:** $q_1 \in F \implies$ **DITERIMA**



---

### e) Diawali `0` dan Diakhiri `1`

* **Komponen Mesin $M$:**
* $Q = \{q_0, q_1, q_2, q_3\}$
* $\Sigma = \{0, 1\}$
* $q_0 = q_0$
* $F = \{q_2\}$


* **Fungsi Transisi ($\delta$):**
* $\delta(q_0, 0) = q_1$
* $\delta(q_0, 1) = q_3$
* $\delta(q_1, 0) = q_1$
* $\delta(q_1, 1) = q_2$
* $\delta(q_2, 0) = q_1$
* $\delta(q_2, 1) = q_2$
* $\delta(q_3, 0) = q_3$
* $\delta(q_3, 1) = q_3$


* **Diagram Transisi:**

```text
               0                                      1
             ┌───┐                                  ┌───┐
             ▼   │                                  ▼   │
           ┌───────┐               1            ╔═══════╗
     ┌──0─►│  q1   │ ─────────────────────────► │ ((q2))│
     │     └───────┘ ◄───────────────────────── ╚═══════╝
 ┌───────┐     │                    0
 │  q0   │     │
 └───────┘     │ 1
     │         ▼
     │     ┌───────┐
     └──1─►│  q3   │ (Trap State)
           └───────┘
               ▲   │
               └───┘
               0, 1

```

* **Pengujian String $S = 00101$:**
* $\delta(q_0, 0) \rightarrow q_1$
* $\delta(q_1, 0) \rightarrow q_1$
* $\delta(q_1, 1) \rightarrow q_2$
* $\delta(q_2, 0) \rightarrow q_1$
* $\delta(q_1, 1) \rightarrow q_2$
* **Status Akhir:** $q_2 \in F \implies$ **DITERIMA**



```

```
