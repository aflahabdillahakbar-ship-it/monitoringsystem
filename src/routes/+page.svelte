<script>
	let passwordVisible = false;
	let nomorPendaftaran = ''; // ✅ Tambahkan ini
	let passwordInput = '';
	let isLoggedIn = false;

	let data = [
		{
			nama: 'Aflah Abdillah Akbar',
			nisn: '0073192073',
			nik: '137111570907001',
			tempatLahir: 'Probolinggo',
			tanggalLahir: '2007-06-07',
			nomorPendaftaran: '23212680231',
			jurusan: 'IPS',
			tanggalDaftar: 'Sabtu, 12 Agustus 2023',
			status: 'LULUS',
		},
		{
			nama: 'Acmadinejad',
			nisn: '0073192024',
			nik: '137111570905551',
			tempatLahir: 'Surabaya',
			tanggalLahir: '2007-02-03',
			nomorPendaftaran: '23212680232',
			jurusan: 'IPA',
			tanggalDaftar: 'Selasa, 8 Agustus 2023',
			status: 'TIDAK LULUS',
		},
		{
			nama: 'Sayyidatina Sofiyatus Zahro',
			nisn: '0073192077',
			nik: '137111570907455',
			tempatLahir: 'Sidoarjo',
			tanggalLahir: '2007-08-08',
			nomorPendaftaran: '23212680233',
			jurusan: 'IPA',
			tanggalDaftar: 'Sabtu, 12 Agustus 2023',
			status: 'LULUS',
		},
		{
			nama: 'Nayla Salsabila',
			nisn: '0073192078',
			nik: '137111570907456',
			tempatLahir: 'Lumajang',
			tanggalLahir: '2008-05-07',
			nomorPendaftaran: '23212680234',
			jurusan: 'IPS',
			tanggalDaftar: 'Kamis, 10 Agustus 2023',
			status: 'TIDAK LULUS',
		},
		{
			nama: 'Muhammad Idham Ichsani',
			nisn: '0073193089',
			nik: '137111570902366',
			tempatLahir: 'Lamongan',
			tanggalLahir: '2007-03-09',
			nomorPendaftaran: '23212680235',
			jurusan: 'IPA',
			tanggalDaftar: 'Jumat, 11 Agustus 2023',
			status: 'LULUS',
		},
		{
			nama: 'Najwa Kamila Harun',
			nisn: '0073194589',
			nik: '1371115709052334',
			tempatLahir: 'Paiton',
			tanggalLahir: '2008-05-09',
			nomorPendaftaran: '23212680236',
			jurusan: 'IPA',
			tanggalDaftar: 'Sabtu, 12 Agustus 2023',
			status: 'TIDAK LULUS',
		},
		{
			nama: 'Ichsan Rusli Annadhimi',
			nisn: '0073192743',
			nik: '137111570903428',
			tempatLahir: 'Blitar',
			tanggalLahir: '2007-06-10',
			nomorPendaftaran: '23212680237',
			jurusan: 'IPA',
			tanggalDaftar: 'Senin, 7 Agustus 2023',
			status: 'LULUS',
		},
		{
			nama: 'Aulia Rahmawati',
			nisn: '0073193497',
			nik: '137111570901567',
			tempatLahir: 'Semampir',
			tanggalLahir: '2007-08-09',
			nomorPendaftaran: '23212680238',
			jurusan: 'IPA',
			tanggalDaftar: 'SELASA, 8 Agustus 2023',
			status: 'TIDAK LULUS',
		},
		{
			nama: 'Muhammad Davin Clea',
			nisn: '0073195409',
			nik: '137111570902007',
			tempatLahir: 'Madura',
			tanggalLahir: '2007-17-11',
			nomorPendaftaran: '23212680239',
			jurusan: 'IPA',
			tanggalDaftar: 'Sabtu, 12 Agustus 2023',
			status: 'LULUS',
		},
		{
			nama: 'Muzaki Alfaruqi',
			nisn: '0073192035',
			nik: '137111570902879',
			tempatLahir: 'Lampung',
			tanggalLahir: '2007-12-12',
			nomorPendaftaran: '23212680230',
			jurusan: 'IPS',
			tanggalDaftar: 'Rabu, 9 Agustus 2023',
			status: 'TIDAK LULUS',
		}
	]

	function handleLogin() {
		if (data.find((user) => user.nomorPendaftaran === nomorPendaftaran)) {
			isLoggedIn = true;
		} else {
			alert('Nomor Pendaftaran Tidak Ditemukan!');
		}
	}

	// function togglePassword() {
	// 	passwordVisible = !passwordVisible;
	// }

</script>

<svelte:head>
	<title>PPDB Online MAN 2 kota probolinggo Login</title>
	<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/5.15.3/css/all.min.css" />
	<link href="https://fonts.googleapis.com/css2?family=Inter&display=swap" rel="stylesheet" />
</svelte:head>

<!-- Halaman akan berubah sesuai status login -->
{#if !isLoggedIn}
	<main class="min-h-screen bg-base-200 flex flex-col justify-center items-center font-inter">
		<div class="card w-full max-w-md bg-base-100 shadow-xl p-6">
			<figure class="mb-4">
				<img
					src="logo kemenag 2.png"
					alt="Logo PPDB"
					class="h-12"
					loading="lazy"
				/>
			</figure>

			<h2 class="text-center text-xl text-base-content font-semibold mb-4">
				Selamat datang di<br />PPDB Online<br />MAN 2 kota probolinggo.
			</h2>

			<form on:submit|preventDefault={handleLogin} class="space-y-4">
				<div class="form-control">
					<label class="input input-bordered flex items-center gap-2">
						<i class="fas fa-user text-gray-500"></i>
						<input
							type="text"
							placeholder="Nomor Pendaftran"
							class="grow"
							bind:value={nomorPendaftaran}
							required
						/>
					</label>
				</div>

				<button class="btn btn-primary w-full" type="submit">CARI</button>
				<div class="text text-center mt-2 p-2 text-[12px]">
					Dimohon untuk memastikan nomor pendaftaran anda dengan benar <br />
					Agar tidak terjadi kesalahan dalam proses pencarian
				</div>
			</form>
		</div>
	</main>
    {:else}
	{#each data.filter((user)=>user.nomorPendaftaran == nomorPendaftaran) as user}
   <main class="min-h-screen p-4 font-sans bg-blue-100">


		<div class="max-w-4xl mx-auto bg-white border border-gray-300 p-4 shadow-md">
			<div class="flex flex-col md:flex-row md:space-x-4">
          <div class="flex-1 space-y-4">
            <div class="border border-gray-400 p-2">
              <div class="grid grid-cols-[140px_1fr] gap-x-2 text-[10px] font-bold text-black">
                <div>NOMOR REGISTRASI</div>
                <div class="font-normal tracking-widest">{user.nomorPendaftaran}</div>
                <div>NAMA PESERTA</div>
                <div class="font-normal">{user.nama}</div>
                <div>TEMPAT LAHIR</div>
                <div class="font-normal">{user.tempatLahir}</div>
                <div>TANGGAL LAHIR</div>
                <div class="font-normal">{user.tanggalLahir}</div>
                <div>NISN</div>
                <div class="font-normal tracking-widest">{user.nisn}</div>
                <div>NIK</div>
                <div class="font-normal tracking-widest">{user.nik}</div>
              </div>
            </div>
  
            <div class="border border-gray-400 p-2">
              <div class="grid grid-cols-[140px_1fr] gap-x-2 text-[10px] font-bold text-black">
				<div>SEKOLAH PILIHAN</div>
				<div class="font-normal">MAN 2 KOTA PROBOLINGGO</div>
				<div>ZONASI</div>
				<div class="font-normal">-</div>
				<div>JURUSAN</div>
				<div class="font-normal">{user.jurusan}</div>
				<div>TANGGAL DAFTAR</div>
				<div class="font-normal">{user.tanggalDaftar}</div>
			  </div>
            </div>
		</div>
	
          <div class="flex flex-col space-y-4 mt-4 md:mt-0">
            <div class="border border-gray-400 p-1 flex justify-center items-center">
              <img
                src="Foto Kosong.jpg"
                alt="Foto peserta"
                class="object-contain"
                width="120"
                height="140"
              />
            </div>
            <div class="border border-gray-400 p-1 flex justify-center items-center">
              <img
                src="https://storage.googleapis.com/a1aa/image/f1b887a3-2124-4fd2-3c44-973cefa79974.jpg"
                alt="QR Code"
                class="object-contain"
                width="120"
                height="120"
              />
            </div>
          </div>
        </div>
  
        <div
  class="border border-e-black mt-6 font-bold text-center text-lg py-3 text-white"
  class:bg-green-600={user.status === 'LULUS'}
  class:bg-red-600={user.status === 'TIDAK LULUS'}
>
  ANDA DINYATAKAN {user.status}
</div>


  
        <div class="border border-gray-400 mt-6 p-2 text-[10px] font-bold">
            SIMPAN JAWABAN INI SEBAGAI PENGUMUMAN ATAS SELESAINYA SELEKSI
        </div>
  
        <div class="text-[9px] mt-1 font-normal">
        </div>
    </main>
	{/each}
  {/if}

<style>
	.font-inter {
		font-family: 'Inter', sans-serif;
	}
</style>