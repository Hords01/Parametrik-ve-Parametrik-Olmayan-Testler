# 🧠 Mood Testi

İki yığına ilişkin **dağılış (varyans) parametrelerinin eşitliği** için yapılabilecek testlerden biri **Mood testidir**.
Mood testi, iki bağımsız örneklemin **medyanlarının aynı olduğu varsayımı** altında, dağılışların benzer olup olmadığını inceler.

Bu test, parametrik olmayan yöntemler arasında yer alır ve özellikle **verilerin normal dağılmadığı** veya **varyansların homojen olmadığı** durumlarda tercih edilir.

---

## 🎯 Amaç

Mood testi, iki grubun dağılış genişliklerinin (yani varyanslarının) eşit olup olmadığını test eder. 
Parametrik testlerdeki gibi normal dağılım varsayımı aranmaz. Bu nedenle, örneklemler küçük ya da dağılım çarpık olsa bile uygulanabilir. 

---

## ⚙️ Varsayımlar

1. İki örneklem **bağımsız** olmalıdır.
2. Veriler **en az ordinal (sıralı)** ölçekte olmalıdır.
3. Grupların medyanları birbirine eşit olmalıdır (ön koşul).

Hipotezler:

```math
H_0: \sigma_1^2 = \sigma_2^2 
H_1: \sigma_1^2 \neq \sigma_2^2

H_0: İki grubun dağılışlarının (varyanslarının) eşit olduğunu
H_1: İki grubun dağılışlarının (varyanslarının) eşit olmadığını ifade eder.

## 🧮 Testin Uygulanışı (Adım Adım)

Mood testi, verilerin medyan etrafındaki dağılış farklarını inceler. İşte adım adım uygulanışı:

---

### 1️⃣ Verilerin Hazırlanması
- İki bağımsız grubun gözlemleri belirlenir:  
  \( X_1 = \{x_{11}, x_{12}, ..., x_{1n_1}\} \) ve  
  \( X_2 = \{x_{21}, x_{22}, ..., x_{2n_2}\} \)
- Örneklerin boyutları farklı olabilir.

---

### 2️⃣ Genel Medyanın Hesaplanması
- Tüm gözlemler birleştirilir:  
  \( X = X_1 \cup X_2 \)  
- Genel medyan \( \tilde{X} \) hesaplanır:  
  \[
  \tilde{X} = \text{Medyan}(X)
  \]

---

### 3️⃣ Gözlemlerin Sınıflandırılması
- Her gözlem, genel medyandan büyük veya küçük olarak sınıflandırılır:  

\[
S_{ij} =
\begin{cases} 
1 & \text{eğer } x_{ij} > \tilde{X} \\
0 & \text{eğer } x_{ij} \le \tilde{X}
\end{cases}
\]

- Burada \(i = 1,2\) (grup numarası), \(j = 1, ..., n_i\) (gözlem numarası).

---

### 4️⃣ Ki-Kare Tablosunun Oluşturulması
- Her grup için medyanın altında ve üstünde kalan gözlem sayıları sayılır:  

\[
O_{11} = \text{Grup 1'de medyanın altında kalan sayısı}, \quad
O_{12} = \text{Grup 1'de medyanın üstünde kalan sayısı}
\]

\[
O_{21} = \text{Grup 2'de medyanın altında kalan sayısı}, \quad
O_{22} = \text{Grup 2'de medyanın üstünde kalan sayısı}
\]

- Beklenen değerler (\(E_{ij}\)) toplam gözlemlere göre hesaplanır:  

\[
E_{ij} = \frac{(\text{Grup i toplamı}) \cdot (\text{Kategori j toplamı})}{\text{Toplam gözlem sayısı}}
\]

---

### 5️⃣ Mood İstatistiğinin Hesaplanması
- Ki-kare istatistiği hesaplanır:  

\[
\chi^2 = \sum_{i=1}^{2} \sum_{j=1}^{2} \frac{(O_{ij} - E_{ij})^2}{E_{ij}}
\]

- Bu istatistik, gözlenen ve beklenen değerler arasındaki farkı ölçer.

---

### 6️⃣ P-değerinin Hesaplanması ve Karar
- Hesaplanan \(\chi^2\) değeri kullanılarak p-değeri bulunur.  
- Karar kriteri:  
  - \(p < 0.05 \Rightarrow H_0\) reddedilir (medyanlar farklıdır)  
  - \(p \ge 0.05 \Rightarrow H_0\) kabul edilir (medyanlar arasında fark yoktur)

---

**Özet:**  
Mood testi, verileri medyanın altında veya üstünde şeklinde sınıflandırarak gruplar arasındaki dağılış farkını ölçer. Ki-kare istatistiği ile yapılan bu ölçüm, parametrik varsayımlara bağlı kalmadan güvenilir sonuç verir
