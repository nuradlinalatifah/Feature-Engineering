## Analisis Hasil Feature Engineering

**1. Tokenization**

Pada tahap tokenization, teks berita yang telah melalui proses preprocessing dipecah menjadi token atau kata-kata. Setiap kata diubah menjadi huruf kecil agar formatnya seragam. Hasil tokenization ini digunakan sebagai input untuk membangun model Word2Vec dan FastText.

**2. Word2Vec**

Model Word2Vec digunakan untuk mengubah kata menjadi vektor numerik berdimensi 100. Berdasarkan hasil pengujian, model memiliki 640 kata dalam kosakata (*vocabulary*). Kata-kata yang memiliki kemiripan berdasarkan hasil model dapat dilihat menggunakan fungsi `similar_by_key()`. Hasil tersebut menunjukkan hubungan antarkata berdasarkan pola konteks yang dipelajari dari kumpulan teks berita.

**3. Document Vector Word2Vec**

Pada tahap ini, setiap dokumen berita diubah menjadi vektor numerik dengan menghitung rata-rata vektor dari kata-kata yang terdapat di dalamnya. Hasilnya adalah representasi numerik dengan 100 fitur untuk setiap dokumen. Vektor tersebut dapat digunakan sebagai masukan untuk proses analisis data atau pemodelan machine learning selanjutnya.

**4. Visualisasi Word2Vec dengan UMAP**

UMAP digunakan untuk memproyeksikan vektor kata ke dalam dua dimensi agar lebih mudah divisualisasikan. Pada grafik, setiap titik merepresentasikan sebuah kata. Kata-kata yang posisinya berdekatan memiliki representasi vektor yang relatif mirip menurut model, meskipun kedekatan tersebut tidak selalu berarti kata-kata itu memiliki makna yang sama.

**5. FastText**

FastText digunakan untuk menghasilkan representasi vektor kata dengan mempertimbangkan informasi kata dan potongan karakter (*character n-grams*). Model yang digunakan memiliki dimensi vektor 100, dengan ukuran *n-gram* dari 3 hingga 6 karakter. Pendekatan ini memungkinkan FastText mempelajari pola kata melalui susunan karakternya, selain pola konteks dalam teks. Hasil kemiripan kata dapat diperiksa menggunakan fungsi `similar_by_key()`.

**6. Document Vector FastText**

Sama seperti Word2Vec, setiap dokumen berita direpresentasikan sebagai vektor dengan menghitung rata-rata vektor kata yang terdapat di dalam dokumen. Hasilnya berupa 100 fitur untuk setiap dokumen. Representasi ini dapat digunakan dalam proses pengolahan teks lebih lanjut.

**7. Visualisasi FastText dengan UMAP**

Visualisasi UMAP digunakan untuk menampilkan vektor kata FastText dalam dua dimensi. Grafik membantu melihat pola kedekatan antarkata berdasarkan representasi yang dipelajari model. Pola yang terbentuk dapat digunakan untuk mengamati hubungan antarkata, tetapi interpretasinya tetap perlu disesuaikan dengan kata-kata yang muncul pada grafik.

**Kesimpulan**

Berdasarkan tahapan yang telah dilakukan, Word2Vec dan FastText dapat digunakan untuk mengubah teks berita hasil preprocessing menjadi representasi numerik. Word2Vec mempelajari representasi kata berdasarkan konteksnya, sedangkan FastText juga mempertimbangkan potongan karakter kata. Kedua model menghasilkan vektor berdimensi 100 dan dapat digunakan untuk membentuk *document vector*. Visualisasi UMAP membantu mengamati pola kedekatan antarkata dalam ruang dua dimensi. Dengan demikian, hasil feature engineering ini dapat menjadi dasar untuk analisis teks atau pemodelan machine learning selanjutnya.
