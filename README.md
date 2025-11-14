# Hargana Hotel Dataset

## Deskripsi

Dataset ini berisi kumpulan data hotel di Bandung yang dikumpulkan untuk proyek **Hargana Hotel**. Tujuan utamanya adalah untuk membangun dan menganalisis sistem **Dynamic Pricing berbasis Kecerdasan Buatan (AI)** dalam industri perhotelan.

Dataset mencakup informasi lengkap tentang:

- Metadata dan fasilitas hotel (rating, lokasi, dan fasilitas)
- Data harga historis dari berbagai platform online
- Ulasan pelanggan
- Tempat menarik (POI) di sekitar hotel
- Data cuaca historis Bandung

## Struktur Dataset

Dataset terdiri dari beberapa file CSV yang saling terkait dengan **hotel_id** dan **Date** sebagai kunci utama.

### 1. hotels_data_en.csv & hotels_data_id.csv

File master metadata hotel dalam dua bahasa: Inggris dan Indonesia.

**Kolom utama:**

- `hotel_id`: ID unik Google Place (Primary Key)
- `rating`: Rating rata-rata (1-5)
- `reviews_count`: Jumlah total ulasan
- `location`: Alamat lengkap
- `contact`: Nomor telepon
- `category`: Kategori hotel (mis. "Hotel bintang 4")
- `amenities`: Daftar fasilitas
- `coordinates`: (Latitude, Longitude)
- `thumbnails`: URL gambar hotel

### 2. hotel_price.csv

Data runtun waktu harga hotel utama dari berbagai platform.

**Kolom utama:**

- `Price`: Harga utama (biasanya dari Trivago)
- `Hotel_id`: ID unik hotel (Foreign Key)
- `Date`: Tanggal pengambilan harga

### 3. hotels_reviews.csv

Berisi ulasan pelanggan dalam format lebar (wide format).

**Kolom utama:**

- `Hotel_id`: ID unik hotel
- `Reviews/X/reviewer`: Nama pengulas
- `Reviews/X/date`: Tanggal ulasan
- `Reviews/X/rating`: Rating yang diberikan (1-5)
- `Reviews/X/text`: Isi ulasan

### 4. nearby_places_en.csv & nearby_places_id.csv

Memetakan hotel dengan **Points of Interest (POI)** di sekitarnya.

**Kolom utama:**

- `hotel_place_id`: ID unik Google Place (Foreign Key)
- `nearby_place_name`: Nama POI
- `nearby_place_type`: Kategori POI (mis. "Belanja", "Restoran")
- `distance`: Jarak dari hotel ke POI (km)
- `latitude`: Garis lintang POI
- `longitude`: Garis bujur POI

### 5. weather_en.csv & weather_id.csv

Data cuaca historis Bandung sebagai fitur tambahan untuk model harga.

**Kolom utama:**

- `date`: Tanggal pencatatan
- `temperature_c`: Suhu rata-rata (°C)
- `rain_mm`: Curah hujan (mm)
- `humidity_pct`: Kelembapan (%)
- `weather_condition`: Deskripsi cuaca (Cerah, Hujan, dll.)
- `weather_encoded`: Representasi numerik cuaca

## Potensi Penggunaan

Dataset ini dapat digunakan untuk berbagai tugas analisis dan machine learning:

- **Prediksi Harga Hotel:** Membangun model regresi untuk memperkirakan harga berdasarkan cuaca, musim, rating, fasilitas, dan kompetitor.
- **Analisis Sentimen:** Mengolah teks ulasan pelanggan untuk memahami persepsi terhadap layanan hotel.
- **Sistem Rekomendasi:** Merekomendasikan hotel berdasarkan lokasi atau preferensi fasilitas.
- **Analisis Kompetitor:** Menganalisis strategi harga dari berbagai platform pemesanan online.
