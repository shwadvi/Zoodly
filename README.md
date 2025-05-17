# Zoodly<?php
// config.php
$your_percentage = 0.15; // نسبتك في المكسب
$whatsapp_number = "201000000000"; // رقمك واتساب
$api_key = "YOUR_SUPPLIER_API_KEY"; // API المورد

function getServiceList() {
    // مثال لاستدعاء الخدمات من المورد
    $services = file_get_contents("https://supplierapi.com/api/services?key=YOUR_SUPPLIER_API_KEY");
    return json_decode($services, true);
}

function calculateProfit($base_price) {
    global $your_percentage;
    return $base_price + ($base_price * $your_percentage);
}
?>
<!-- index.html -->
<!DOCTYPE html>
<html lang="ar">
<head>
    <meta charset="UTF-8">
    <title>سيرفر التزويد والشحن</title>
</head>
<body style="direction: rtl; font-family: Arial;">
    <h1>🔥 خدمات سوشيال ميديا وشحن ألعاب 🔥</h1>
    <p>تواصل معنا واتساب مباشر: <a href="https://wa.me/201000000000">اضغط هنا</a></p>

    <h2>اختر الخدمة 👇</h2>
    <form action="order.php" method="POST">
        <label>الخدمة:</label>
        <select name="service_id">
            <!-- هنا هنملأ الخيارات من PHP -->
        </select><br>
        <label>الكمية:</label>
        <input type="number" name="quantity"><br>
        <input type="submit" value="اطلب الآن">
    </form>
</body>
</html>
