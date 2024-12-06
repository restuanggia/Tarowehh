<template>
  <div class="detail-pesanan">
    <Navbar />
    <div class="container mt-5">
      <div class="row justify-content-center">
        <div class="col-md-8">
          <h2>Detail <strong>Pesanan</strong></h2>
          <div v-if="pesanan" class="mt-4">
            <h4>Nama Pemesan: {{ pesanan.nama }}</h4>
            <h5>Nomor Meja: {{ pesanan.noMeja }}</h5>
            <h5>Tanggal Pesanan: {{ pesanan.tanggal }}</h5>
            <hr />
            <h4>Detail Keranjang</h4>
            <table class="table">
              <thead>
                <tr>
                  <th scope="col">#</th>
                  <th scope="col">Makanan</th>
                  <th scope="col">Jumlah</th>
                  <th scope="col">Harga</th>
                  <th scope="col">Total Harga</th>
                </tr>
              </thead>
              <tbody>
                <tr v-for="(item, index) in pesanan.keranjangs" :key="index">
                  <th>{{ index + 1 }}</th>
                  <td>{{ item.products.nama }}</td>
                  <td>{{ item.jumlah_pemesanan }}</td>
                  <td>Rp. {{ item.products.harga }}</td>
                  <td>Rp. {{ item.products.harga * item.jumlah_pemesanan }}</td>
                </tr>
              </tbody>
            </table>
            <hr />
            <h5>Total Harga: Rp. {{ pesanan.totalHarga }}</h5>
          </div>
          <div v-else>
            <p>Loading...</p>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import Navbar from "@/components/Navbar.vue";

export default {
  name: "DetailPesanan",
  components: {
    Navbar,
  },
  data() {
    return {
      pesanan: null,
    };
  },
  mounted() {
    const pesananId = this.$route.params.id; // Mengambil ID pesanan dari URL
    this.loadPesananDetail(pesananId);
  },
  methods: {
    loadPesananDetail(id) {
      // Ambil riwayat pesanan dari localStorage
      const riwayat = localStorage.getItem("riwayatPesanan");
      if (riwayat) {
        const parsedRiwayat = JSON.parse(riwayat);
        // Cari pesanan berdasarkan ID
        this.pesanan = parsedRiwayat.find(
          (pesanan) => pesanan.id === parseInt(id)
        );
      }
    },
  },
};
</script>

<style scoped>
.detail-pesanan {
  margin-top: 20px;
}
</style>
