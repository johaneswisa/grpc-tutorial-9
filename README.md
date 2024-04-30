# Reflection Tutorial 9

1. What are the key differences between unary, server streaming, and bi-directional streaming RPC (Remote Procedure Call) methods, and in what scenarios would each be most suitable?

Unary RPC: Melibatkan satu permintaan dari klien dan satu tanggapan dari server. Cocok untuk interaksi permintaan-respons sederhana di mana klien membutuhkan respons segera.

Server Streaming RPC: Melibatkan satu permintaan dari klien dan stream responses dari server. Cocok untuk skenario di mana server perlu mengirimkan sejumlah besar data kembali ke klien tanpa menunggu permintaan tambahan.

Bidirectional Streaming RPC: Melibatkan stream requests dari klien dan stream responses dari server. Cocok untuk komunikasi real-time atau skenario di mana baik klien maupun server perlu mengirim aliran data yang kontinu.

2. What are the potential security considerations involved in implementing a gRPC service in Rust, particularly regarding authentication, authorization, and data encryption?

Autentikasi: Memverifikasi identitas klien dan server menggunakan mekanisme seperti JWT, OAuth, atau sertifikat TLS klien.

Otorisasi: Mengendalikan akses ke sumber daya berdasarkan identitas dan izin klien.

Enkripsi Data: Memastikan kerahasiaan dan integritas data yang dipertukarkan antara klien dan server menggunakan TLS.

3. What are the potential challenges or issues that may arise when handling bidirectional streaming in Rust gRPC, especially in scenarios like chat applications?

Mengelola beberapa aliran yang berjalan bersamaan dan memastikan sinkronisasi antara klien dan server.

Menangani kesalahan dan waktu habis secara anggun, terutama dalam koneksi yang berlangsung lama seperti aplikasi obrolan.

Memastikan manajemen sumber daya yang tepat untuk mencegah kebocoran memori atau kehabisan sumber daya.

4. What are the advantages and disadvantages of using the tokio_stream::wrappers::ReceiverStream for streaming responses in Rust gRPC services?

Keuntungan: Memberikan cara yang nyaman untuk mengonversi Receiver dari library tokio menjadi stream yang kompatibel dengan gRPC.

Kerugian: Fleksibilitas terbatas dibandingkan dengan implementasi stream kustom, mungkin tidak mendukung manipulasi atau transformasi stream lanjutan.

5. In what ways could the Rust gRPC code be structured to facilitate code reuse and modularity, promoting maintainability and extensibility over time?

Mendefinisikan komponen yang dapat digunakan kembali seperti antarmuka layanan, definisi pesan, dan middleware.

Menyembunyikan fungsionalitas umum di modul atau kotak terpisah.

Menggunakan trait dan generic untuk abstraksi atas implementasi yang berbeda dan mendorong penggunaan kembali kode.

6. In the MyPaymentService implementation, what additional steps might be necessary to handle more complex payment processing logic?

Melakukan manajemen transaksi, error-handling, dan percobaan ulang untuk resilience.

Mengintegrasikan dengan payment gateways atau API eksternal untuk pemrosesan pembayaran.

Mengimplementasikan mekanisme validasi dan verifikasi untuk memastikan integritas transaksi pembayaran.

7. What impact does the adoption of gRPC as a communication protocol have on the overall architecture and design of distributed systems, particularly in terms of interoperability with other technologies and platforms?

* Mendorong arsitektur berorientasi layanan dengan antarmuka dan kontrak yang terdefinisi dengan baik.
* Memfasilitasi pengembangan poliglot dengan menyediakan antarmuka komunikasi yang independen bahasa.
* Mengharuskan adopsi teknologi dan alat yang kompatibel untuk service discovery, load balancing, dan observabilitas.

8. What are the advantages and disadvantages of using HTTP/2, the underlying protocol for gRPC, compared to HTTP/1.1 or HTTP/1.1 with WebSocket for REST APIs?

* Keuntungan HTTP/2: Multiplexing, kompresi header,server push, dan stream prioritization meningkatkan kinerja dan efisiensi.
* Kerugian: Kompleksitas implementasi dan potensi masalah kompatibilitas dengan klien atau proxy yang lebih lama.

9. How does the request-response model of REST APIs contrast with the bidirectional streaming capabilities of gRPC in terms of real-time communication and responsiveness?

* REST API mengikuti model permintaan-respons, yang dapat men-introduce latency untuk komunikasi real-time.
* Streaming bidirectional gRPC memungkinkan komunikasi yang lebih responsif dengan latency yang lebih rendah, membuatnya cocok untuk aplikasi real-time seperti obrolan atau permainan.

10. What are the implications of the schema-based approach of gRPC, using Protocol Buffers, compared to the more flexible, schema-less nature of JSON in REST API payloads?

* Keuntungan: Skema yang diberikan kuat memungkinkan validasi, dokumentasi, dan generasi kode yang lebih baik.
* Kerugian: Kurangnya fleksibilitas dibandingkan dengan JSON, mungkin memerlukan usaha tambahan untuk evolusi skema dan penomoran versi.





