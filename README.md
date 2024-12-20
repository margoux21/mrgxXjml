<html lang="id">
<head>
    <meta charset="UTF-8">
    <title>Indeks Prestasi</title>
    <style>
        body { font-family: Arial, sans-serif; text-align: center; }
        table { margin: 20px auto; border-collapse: collapse; }
        input { margin: 5px; text-align: center; }
    </style>
</head>
<body>
    <table border="1" align="center" width="100%">
        <tr>
            <td width="100%" colspan="4"><h1 align="center">Menghitung Indeks Prestasi</h1></td>
        </tr>
        <tr>
            <td>Quis (10%):</td>
            <td>Tugas (20%):</td>
            <td>UTS (30%):</td>
            <td>UAS (40%):</td>
        </tr>
        <tr>
            <td><input type="text" id="quis" size="10"></td>
            <td><input type="text" id="tugas" size="10"></td>
            <td><input type="text" id="uts" size="10"></td>
            <td><input type="text" id="uas" size="10"></td>
        </tr>
        <tr>
            <td colspan="4" align="center">
                <input type="button" value="Hitung" onclick="hitungtotal()">
                <input type="reset" value="Ulang" onclick="resetForm()">
            </td>
        </tr>
        <tr>
            <td colspan="2" align="center">
                Indeks Prestasi: <input type="text" id="hasilIP" readonly>
            </td>
            <td colspan="2" align="center">
                Keterangan: <input type="text" id="keterangan" readonly>
            </td>
        </tr>
    </table>

    <script>
    function hitungtotal() {
        const quis = parseFloat(document.getElementById('quis').value) || 0;
        const tugas = parseFloat(document.getElementById('tugas').value) || 0;
        const uts = parseFloat(document.getElementById('uts').value) || 0;
        const uas = parseFloat(document.getElementById('uas').value) || 0;

        const totalNilai = (
            (quis * 0.1) + 
            (tugas * 0.2) + 
            (uts * 0.3) + 
            (uas * 0.4)
        );

        let nilaiHuruf = '';
        let keterangan = '';


        if (totalNilai >= 80 && totalNilai <= 100) {
            nilaiHuruf = 'A';
            keterangan = 'Lulus dengan Sangat Baik';
        } else if (totalNilai >= 68 && totalNilai < 80) {
            nilaiHuruf = 'B';
            keterangan = 'Lulus dengan Baik';
        } else if (totalNilai >= 55 && totalNilai < 68) {
            nilaiHuruf = 'C';
            keterangan = 'Lulus dengan Cukup';
        } else if (totalNilai >= 38 && totalNilai < 55) {
            nilaiHuruf = 'D';
            keterangan = 'Lulus dengan Kurang';
        } else if (totalNilai >= 0 && totalNilai < 38) {
            nilaiHuruf = 'E';
            keterangan = 'Tidak Lulus';
        } else {
            nilaiHuruf = 'Tidak Valid';
            keterangan = 'Error';
        }

        document.getElementById('hasilIP').value = `${nilaiHuruf}`;
        document.getElementById('keterangan').value = `${keterangan}`;
    }

    function resetForm() {
        document.getElementById('hasilIP').value = '';
        document.getElementById('keterangan').value = '';
    }
    </script>
</body>
</html>
