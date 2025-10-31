<?php
session_start();

$nim = $password = "";
$nim_err = $password_err = $login_err = "";


if(isset($_SESSION["loggedin"]) && $_SESSION["loggedin"] === true){
    $role = $_SESSION["role"];
    if ($role === 'ADMIN') { header("location: admin_dashboard.php"); } 
    elseif ($role === 'PANITIA') { header("location: panitia_dashboard.php"); } 
    else { header("location: dashboard.php"); }
    exit;
}

require_once "connect.php"; 

if($_SERVER["REQUEST_METHOD"] == "POST"){

    if(empty(trim($_POST["nim"]))){ $nim_err = "Mohon masukkan NIM/Email."; } else{ $nim = trim($_POST["nim"]); }
    if(empty(trim($_POST["password"]))){ $password_err = "Mohon masukkan password."; } else{ $password = trim($_POST["password"]); }
    

    if(empty($nim_err) && empty($password_err)){

        $sql = "SELECT id, nim, nama_lengkap, password, email_kampus, no_hp, role FROM tabel_user WHERE nim = ? OR email_kampus = ?";
        
        if($stmt = $conn->prepare($sql)){
            $stmt->bind_param("ss", $param_nim, $param_nim);
            $param_nim = $nim;
            
            if($stmt->execute()){
                $stmt->store_result();
                
                if($stmt->num_rows == 1){                    
                    $stmt->bind_result($id, $nim_db, $nama_db, $hashed_password, $email, $no_hp, $role_db);
                    if($stmt->fetch()){

                        if(password_verify($password, $hashed_password)){

                            session_regenerate_id();
                            $_SESSION["loggedin"] = true;
                            $_SESSION["id"] = $id;
                            $_SESSION["nim"] = $nim_db;
                            $_SESSION["nama"] = $nama_db;
                            $_SESSION["email_kampus"] = $email;
                            $_SESSION["no_hp"] = $no_hp;
                            $_SESSION["role"] = $role_db;


                            if ($role_db === 'ADMIN') {
                                header("location: admin_dashboard.php");
                            } elseif ($role_db === 'PANITIA') {
                                header("location: panitia_dashboard.php");
                            } else {
                                header("location: dashboard.php");
                            }
                            exit; 
                        } else{
                            $login_err = "NIM/Email atau Password salah.";
                        }
                    }
                } else{
                    $login_err = "NIM/Email atau Password salah.";
                }
            } else{
                $login_err = "Oops! Terjadi kesalahan pada database.";
            }
            $stmt->close();
        }
    }
    $conn->close();
}
?>
<!DOCTYPE html>
<html lang="id">
<head>
    <title>Login Sistem Event Kampus</title>
    <script src="https://cdn.tailwindcss.com"></script>
</head>
<body class="bg-gray-100 flex items-center justify-center min-h-screen p-4 sm:p-8">
    <div class="w-full max-w-sm md:max-w-md"> 
        <div class="bg-white p-6 sm:p-8 rounded-xl shadow-2xl border border-gray-200">
            <h1 class="text-2xl sm:text-3xl font-bold text-indigo-700 text-center mb-2">Login</h1>
            <p class="text-sm sm:text-base text-gray-500 text-center mb-6">Masuk untuk mengakses Event Kampus.</p>
            <?php if(isset($_GET['registered'])): ?>
            <div class="bg-green-100 border-l-4 border-green-500 text-green-700 p-4 mb-4" role="alert">
                <p>Pendaftaran berhasil! Silakan login.</p>
            </div>
            <?php endif; ?>
            <?php if(!empty($login_err)): ?>
            <div class="bg-red-100 border-l-4 border-red-500 text-red-700 p-4 mb-4" role="alert"><p><?php echo $login_err; ?></p></div>
            <?php endif; ?>
            <form action="<?php echo htmlspecialchars($_SERVER["PHP_SELF"]); ?>" method="POST" class="space-y-6">
                <div>
                    <label class="block text-sm font-medium text-gray-700">NIM atau Email Kampus</label>
                    <input type="text" name="nim" value="<?php echo $nim; ?>" required class="mt-1 block w-full border border-gray-300 rounded-md shadow-sm p-3 focus:ring-indigo-500">
                    <?php if(!empty($nim_err)): ?><p class="text-xs text-red-600 mt-1"><?php echo $nim_err; ?></p><?php endif; ?>
                </div>
                <div>
                    <label class="block text-sm font-medium text-gray-700">Password</label>
                    <input type="password" name="password" required class="mt-1 block w-full border border-gray-300 rounded-md shadow-sm p-3 focus:ring-indigo-500">
                    <?php if(!empty($password_err)): ?><p class="text-xs text-red-600 mt-1"><?php echo $password_err; ?></p><?php endif; ?>
                </div>
                <button type="submit" class="w-full py-3 text-lg font-medium text-white bg-indigo-600 rounded-md hover:bg-indigo-700 transition duration-150">
                    Login
                </button>
            </form>
            <div class="mt-6 text-center text-sm">
                <p class="text-gray-500">Belum punya akun? <a href="register.php" class="font-medium text-indigo-600 hover:text-indigo-500">Daftar Sekarang</a></p>
            </div>
        </div>
    </div>
</body>
</html>