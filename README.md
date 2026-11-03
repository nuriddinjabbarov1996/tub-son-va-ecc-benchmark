# ECC Skalyar Ko'paytirish Algoritmlari Benchmarki

**Tadqiqot va Tahlil Dasturi (Jupyter Notebook)**

Ushbu loyiha Elliptik Egri Chiziq Kriptografiyasida (ECC) skalyar ko'paytirish algoritmlarining tezligi, samaradorligi va xotira sarfini qiyosiy tahlil qilishga qaratilgan[cite: 3]. Dastur turli xil algoritmlarni sof Python (va `gmpy2`) hamda haqiqiy kriptografik kutubxonalar (OpenSSL, libsecp256k1) bilan taqqoslaydi[cite: 3, 4].

## 📌 Qo'llab-quvvatlanuvchi Egri Chiziqlar (Curves)
Tahlil asosan quyidagi ikkita mashhur standart egri chiziqlar ustida olib boriladi[cite: 3]:
* **secp256k1** (Bitcoin va boshqa kriptovalyutalarda ishlatiladi)[cite: 3]
* **P-256** (NIST standarti)[cite: 3]

## 🚀 O'rganilgan Algoritmlar
Dastur qisqa Veyershtrass (Weierstrass) shakli va Jacobian koordinatalaridan foydalangan holda quyidagi skalyar ko'paytirish usullarini sinovdan o'tkazadi[cite: 3]:
* **Binary:** Chapdan o'ngga "double-and-add" usuli[cite: 3].
* **wNAF (w-ary Non-Adjacent Form):** Oyna kengligi (w) asosidagi NAF algoritmi[cite: 3].
* **FW (Fixed-window):** Belgisiz k-ary usuli[cite: 3].
* **Ladder:** Montgomery ladder usuli[cite: 3].
* **GLV (wNAF bilan):** Faqat `secp256k1` endomorfizmi uchun tezlashtirilgan usul[cite: 3].
* **Comb (Lim–Lee):** Faqat fiksirlangan bazaviy nuqta (G) uchun ishlatiladigan algoritm[cite: 3].

## 📊 Benchmark va Tahlil (Analyze.py)
Jupyter notebook va `analyze.py` skripti orqali quyidagi 7 ta asosiy yo'nalish bo'yicha (S1-S7) statistik natijalar (CSV/Markdown) va grafiklar shakllantiriladi[cite: 3, 4]:
1. **S1 (Vaqt statistikasi):** Bajarilish vaqtining o'rtacha va mediana ko'rsatkichlari, o'lchov shovqini (noise)[cite: 4].
2. **S2 (Tezlashish):** Algoritmlarning standart Binary usuliga nisbatan tezlashish darajasi[cite: 4].
3. **S3 (Amal xarajatlari):** Bitta guruh amali (qo'shish, ikkilantirish) uchun ketadigan vaqt (tau) va "kappa" nisbati[cite: 4].
4. **S4 (Zichlik):** wNAF da noldan farqli raqamlar zichligini nazariy va amaliy taqqoslash[cite: 4].
5. **S5 (Optimal w):** Oyna kengligining (w) eng optimal qiymatini tajriba va teorema asosida aniqlash[cite: 4].
6. **S6 (Xotira budjeti):** Belgilangan xotira cheklovlari (budget) ostida eng yaxshi algoritmni tanlash[cite: 4].
7. **S7 (Bashoratlash):** Bajarilish vaqtini Linear Regression (Chiziqli regressiya) modeli orqali bashorat qilish (CV va LOGO yondashuvlari)[cite: 4].

## 🛠 O'rnatish va Ishlatish
Dastur ishlashi uchun quyidagi kutubxonalar talab etiladi[cite: 3]:
`gmpy2`, `coincurve` (libsecp256k1), `cryptography` (OpenSSL), `numpy`, `pandas`, `scipy`, `scikit-learn`, `matplotlib`[cite: 3].

1. Loyihani yuklab oling va barcha kutubxonalarni o'rnating.
2. `ecbench_tajriba.ipynb` faylini ochib, barcha kataklarni (Run All) ishga tushiring[cite: 3].
3. Dastur to'liq tekshiruv (yoki tezkor sinov) o'tkazib, natijalarni `ecbench_natijalar` jildiga `summary.md` va `.csv` formatlarida saqlaydi[cite: 3, 4].
