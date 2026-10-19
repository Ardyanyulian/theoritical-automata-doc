# BAB 1

---

## 1. Himpunan (Set Theory)

### A. Keanggotaan Himpunan
* **Definisi:** Himpunan adalah kumpulan objek/elemen tanpa urutan atau struktur khusus.
* **Notasi Keanggotaan:**
  * $x \in S$ artinya $x$ adalah anggota dari $S$.
  * $x \notin S$ artinya $x$ bukan anggota dari $S$.

### B. Notasi Pembentuk Himpunan
* **Bentuk Umum:** $S = \{i : i > 0, i \text{ adalah bilangan genap}\}$
* **Simbol `:`** dibaca *"sedemikian rupa sehingga"* atau *"dengan syarat"*.
* **Penulisan Langsung:**
  * $S = \{0, 1, 2\}$ (penulisan anggota secara eksplisit).
  * $\{\dots\}$ digunakan jika polanya sudah jelas, contoh:
    * $\{a, b, c, \dots, z\}$
    * $\{2, 4, 6, \dots, n\}$

### C. Operasi Dasar Himpunan
* **Union (Gabungan) $\cup$:** Menggabungkan semua anggota.
  $$S_1 \cup S_2 = \{x : x \in S_1 \text{ atau } x \in S_2\}$$
* **Intersection (Irisan) $\cap$:** Mengambil anggota yang ada di kedua himpunan.
  $$S_1 \cap S_2 = \{x : x \in S_1 \text{ dan } x \in S_2\}$$
* **Selisih (Difference) $-$:** Anggota yang ada pada $S_1$ tetapi tidak ada pada $S_2$.
  $$S_1 - S_2 = \{x : x \in S_1 \text{ dan } x \notin S_2\}$$

### D. Himpunan Semesta, Komplemen, dan Himpunan Kosong
* **Himpunan Semesta ($U$):** Himpunan yang memuat seluruh elemen pada topik pembahasan.
* **Komplemen ($\overline{S}$):** Semua elemen dalam semesta ($U$) yang tidak ada di dalam $S$.
* **Himpunan Kosong ($\emptyset$):** Himpunan yang tidak memiliki anggota sama sekali ($\vert{}\emptyset\vert{} = 0$).

### E. Hukum De Morgan
1. $\overline{S_1 \cup S_2} = \overline{S_1} \cap \overline{S_2}$
2. $\overline{S_1 \cap S_2} = \overline{S_1} \cup \overline{S_2}$

### F. Hubungan Antar Himpunan
* **Subset ($\subseteq$):** $S_1 \subseteq S$ artinya seluruh anggota $S_1$ ada di $S$.
* **Proper Subset ($\subset$):** $S_1 \subset S$ artinya $S_1$ adalah subset dari $S$, tetapi $S_1 \neq S$.
* **Disjoint (Saling Lepas):** Tidak ada anggota yang sama ($S_1 \cap S_2 = \emptyset$).

### G. Ukuran & Powerset
* **Kardinalitas ($\vert{}S\vert{}$):** Jumlah anggota dalam himpunan $S$.
* **Powerset ($2^S$):** Himpunan dari semua kombinasi subset dari $S$ (termasuk $\emptyset$ dan $S$ itu sendiri).
* **Rumus Jumlah Powerset:** $\vert{}2^S\vert{} = 2^{\vert{}S\vert{}}$
  * *Contoh:* Jika $\vert{}S\vert{} = 3$, maka $\vert{}2^S\vert{} = 2^3 = 8$.

---

## 2. Relasi, Fungsi, dan Kompleksitas

### A. Perkalian Kartesius (Cartesian Product)
Perkalian kartesius $S_1 \times S_2$ menghasilkan himpunan pasangan berurutan:
$$S_1 \times S_2 = \{(x, y) : x \in S_1, y \in S_2\}$$

> **Penting:** Urutan sangat berpengaruh! $(a, b) \neq (b, a)$.

* **Contoh:** 
  * Jika $S_1 = \{2, 4\}$ dan $S_2 = \{2, 3, 5, 6\}$
  * Maka $S_1 \times S_2 = \{(2,2), (2,3), (2,5), (2,6), (4,2), (4,3), (4,5), (4,6)\}$

### B. Fungsi dan Relasi
* **Fungsi ($f : S_1 \rightarrow S_2$):** Setiap input ($x$) memiliki **tepat 1** output ($y$).
  * **Total Function:** Berlaku untuk seluruh elemen di domain $S_1$.
  * **Partial Function:** Hanya berlaku untuk sebagian elemen di $S_1$.
* **Relasi:** Lebih bebas dari fungsi, 1 input ($x$) bisa memiliki banyak output ($y$).

### C. Notasi Pertumbuhan Fungsi (Asymptotic Notation)
Digunakan untuk mengukur seberapa cepat fungsi berkembang saat $n$ bernilai sangat besar:
* **Big-O $O(g(n))$ [Batas Atas]:** $\vert{}f(n)\vert{} \le c \cdot \vert{}g(n)\vert{}$
* **Big-Omega $\Omega(g(n))$ [Batas Bawah]:** $\vert{}f(n)\vert{} \ge c \cdot \vert{}g(n)\vert{}$
* **Big-Theta $\Theta(g(n))$ [Batas Ketat]:** $c_1 \cdot \vert{}g(n)\vert{} \le \vert{}f(n)\vert{} \le c_2 \cdot \vert{}g(n)\vert{}$

* **Contoh:**
  * Jika $f(n) = 2n^3 + 3n$ dan $h(n) = 10n^2 + 100$, maka perkembangan tingkat dominan $f(n)$ dapat dinyatakan dalam notasi pertumbuhan terhadap ordo fungsi terkait.

### D. Relasi Ekuivalen
Memenuhi 3 sifat utama:
1. **Refleksif:** $x \equiv x$
2. **Simetris:** Jika $x \equiv y$, maka $y \equiv x$
3. **Transitif:** Jika $x \equiv y$ dan $y \equiv z$, maka $x \equiv z$

* **Contoh Relasi Modulo:** $x \equiv y \iff x \bmod 3 = y \bmod 3$
  * $2 \equiv 5 \pmod 3$ (karena $2 \bmod 3 = 2$ dan $5 \bmod 3 = 2$).
  * Maka bilangan ini memiliki relasi ekuivalen.

---

## 3. Teori Bahasa & Otomata

### A. Definisi Bahasa (Language)
Bahasa ($L$) adalah himpunan string dari $\Sigma^*$ ($L \subseteq \Sigma^*$). Setiap string dalam $L$ disebut **kalimat (sentence)**.

* **Finite Language (Bahasa Berhingga):** Jumlah kalimat terbatas.
  * *Contoh:* $L = \{a, aab, abb\}$
* **Infinite Language (Bahasa Tak Berhingga):** Jumlah kalimat tidak terbatas.
  * *Contoh:* $L = \{a^n b^n : n \ge 0\} = \{\lambda, ab, aabb, aaabbb, \dots\}$

### B. Operasi pada Bahasa
* **Komplemen ($\overline{L}$):** Semua string di $\Sigma^*$ yang tidak ada di dalam $L$ ($\overline{L} = \Sigma^* - L$).
* **Reversal ($L^R$):** Himpunan string pada $L$ dengan urutan dibalik.
  $$L^R = \{w^R : w \in L\}$$
* **Konkatenasi ($L_1 L_2$):** Menggabungkan setiap string $L_1$ dengan setiap string pada $L_2$.
  $$L_1 L_2 = \{xy : x \in L_1, y \in L_2\}$$
* **Kleene Star Closure ($L^*$):** $L^* = L^0 \cup L^1 \cup L^2 \cup \dots$
* **Positive Closure ($L^+$):** $L^+ = L^1 \cup L^2 \cup L^3 \cup \dots$

### C. Contoh Operasi Bahasa
Diberikan $L = \{a^n b^n : n \ge 0\}$:
* **Konkatenasi ($L^2$):**
  $$L^2 = \{a^n b^n a^m b^m : n \ge 0, m \ge 0\}$$
  *Nilai $n$ dan $m$ bebas (tidak harus sama).*
  * Contoh string valid: `abaabb` (dimana $n=1$ dan $m=2$).
* **Reversal ($L^R$):**
  $$L^R = \{b^n a^n : n \ge 0\}$$
  *(Urutan simbol $a$ dan $b$ dibalik).*

---

## 4. Tata Bahasa (Grammar)

### A. Komponen Grammar
Grammar didefinisikan sebagai $4$-tuple:
$$G = (V, T, S, P)$$

* **$V$ (Variables / Non-Terminals):** Simbol berupa huruf kapital yang masih bisa diurai/diganti.
* **$T$ (Terminals):** Simbol terminal yang merupakan hasil akhir (tidak bisa diganti lagi).
* **$S \in V$ (Start Variable):** Simbol awal untuk memulai derivasi.
* **$P$ (Productions):** Aturan produksi pembentukan string dengan bentuk $\alpha \rightarrow \beta$.

### B. Notasi Derivasi
* $w \Rightarrow z$ : String $w$ diturunkan menjadi $z$ dalam **1 langkah**.
* $w \stackrel{*}{\Rightarrow} z$ : String $w$ diturunkan menjadi $z$ dalam **0 atau beberapa langkah**.
* $L(G)$ : Himpunan semua string terminal yang berhasil diturunkan dari $S$ ($S \stackrel{*}{\Rightarrow} w$).

---

### C. Contoh Derivasi Grammar

#### Contoh 1: Bahasa $L(G) = \{a^n b^n : n \ge 0\}$
* **Grammar $G = (V, T, S, P)$:**
  * $V = \{S\}$
  * $T = \{a, b\}$
  * $S = S$
  * $P = \{S \rightarrow aSb \mid \lambda\}$

* **Langkah Derivasi (Membentuk String `aabb`):**
  1. Mulai dari $S$
  2. Pakai aturan $S \rightarrow aSb \implies aSb$
  3. Pakai aturan $S \rightarrow aSb$ lagi pada $S$ di tengah $\implies aaSbb$
  4. Ganti $S \rightarrow \lambda \implies aa\lambda bb = aabb$
  5. **Hasil akhir:** $S \stackrel{*}{\Rightarrow} aabb$, sehingga bahasa yang dihasilkan $L(G) = \{a^n b^n : n \ge 0\}$.

---

#### Contoh 2: Bahasa $L = \{a^n b^{n+1} : n \ge 0\}$
* **Grammar:**
  * $S \rightarrow Ab$
  * $A \rightarrow aAb \mid \lambda$

* **Contoh Derivasi (Membentuk String `abb`):**
  $$S \Rightarrow Ab \Rightarrow aAbb \Rightarrow a(\lambda)bb = abb$$

---

#### Contoh 3: Bahasa Jumlah $a$ dan $b$ Sama (Tanpa Urutan)
* **Deskripsi Bahasa:** $L = \{w : n_a(w) = n_b(w)\}$
* **Grammar:**
  $$S \rightarrow SS \mid aSb \mid bSa \mid \lambda$$

* **Derivasi Dini (Misal String `abba`):**
  1. $S \Rightarrow aSb$
  2. $aSb \Rightarrow a(bSa)b = abSab$
  3. $abSab \Rightarrow ab(\lambda)ab = abba$
  4. **Hasil:** $S \stackrel{*}{\Rightarrow} abba$

---

#### Contoh 4: Grammar Ekuivalen
Dua grammar $G_1$ dan $G_2$ dikatakan **ekuivalen** jika menghasilkan bahasa yang sama:
$$L(G_1) = L(G_2)$$

* **Grammar:**
  * $S \rightarrow aAb \mid \lambda$
  * $A \rightarrow aAb \mid \lambda$

* **Derivasi String `aabb` ($n=2$):**
  1. $S \Rightarrow aAb$
  2. $aAb \Rightarrow a(aAb)b = aaAbb$
  3. $aaAbb \Rightarrow aa(\lambda)bb = aabb$
  4. **Hasil:** $S \stackrel{*}{\Rightarrow} aabb$
