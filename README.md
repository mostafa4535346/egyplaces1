<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>Find Places in Egypt</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 0;
            background-color: #f4f4f9;
        }
        header {
            background-color: #2c3e50;
            color: white;
            padding: 10px 20px;
            text-align: center;
        }
        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 20px;
        }
        select, input[type="text"], input[type="number"], input[type="file"], button {
            padding: 10px;
            width: 100%;
            margin-bottom: 10px;
            border-radius: 5px;
            border: 1px solid #ccc;
        }
        .place-form {
            background-color: #fff;
            padding: 20px;
            border-radius: 5px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
        }
        .place-form h2 {
            margin-bottom: 20px;
        }
        .places-list {
            background-color: #fff;
            padding: 20px;
            border-radius: 5px;
            margin-top: 20px;
        }
        .place-item {
            border-bottom: 1px solid #ddd;
            padding: 10px 0;
        }
        footer {
            background-color: #2c3e50;
            color: white;
            text-align: center;
            padding: 10px;
            position: fixed;
            width: 100%;
            bottom: 0;
        }
    </style>
</head>
<body>
    <header>
        <h1>Find Places in Egypt</h1>
    </header>
    
    <div class="container">
        <div class="language-selection">
            <label for="language">Choose Language:</label>
            <select id="language" onchange="changeLanguage()">
                <option value="en">English</option>
                <option value="ar">Arabic</option>
            </select>
        </div>

        <!-- Place adding form -->
        <div class="place-form">
            <h2>Add a Place</h2>
            <form id="placeForm">
                <label for="placeType">Place Type:</label>
                <select id="placeType" required>
                    <option value="restaurant">Restaurant</option>
                    <option value="supermarket">Supermarket</option>
                    <option value="barbershop">Barbershop</option>
                </select>

                <label for="placeName">Place Name:</label>
                <input type="text" id="placeName" placeholder="Enter the place name" required>

                <label for="buildingNumber">Building Number:</label>
                <input type="number" id="buildingNumber" placeholder="Enter building number" required>

                <label for="mobileNumber">Mobile Number:</label>
                <input type="text" id="mobileNumber" placeholder="Enter mobile number" required>

                <label for="placeImage">Upload Image (Optional):</label>
                <input type="file" id="placeImage">

                <button type="submit">Add Place</button>
            </form>
        </div>

        <!-- Display list of places -->
        <div class="places-list" id="placesList">
            <h2>Real Places in Egypt:</h2>
            <div class="place-item">
                <h3>El Borg Restaurant</h3>
                <p>Location: 15 El-Mohandeseen, Cairo</p>
                <p>Type: Restaurant</p>
                <p>Building Number: 15</p>
                <p>Mobile: +20 100 1234567</p>
            </div>
            <div class="place-item">
                <h3>Carrefour Supermarket</h3>
                <p>Location: 12 Maadi, Cairo</p>
                <p>Type: Supermarket</p>
                <p>Building Number: 12</p>
                <p>Mobile: +20 100 7654321</p>
            </div>
            <div class="place-item">
                <h3>Mr. T's Barbershop</h3>
                <p>Location: 20 Zamalek, Cairo</p>
                <p>Type: Barbershop</p>
                <p>Building Number: 20</p>
                <p>Mobile: +20 100 9876543</p>
            </div>
        </div>
    </div>

    <footer>
        <p>Developed by: Mostafa Ahmed</p>
        <p>Contact: 01033022988</p>
    </footer>

    <script>
        // Change website language
        function changeLanguage() {
            const language = document.getElementById("language").value;
            if (language === "ar") {
                document.querySelector("header h1").textContent = "ابحث عن الأماكن في مصر";
                document.querySelector(".place-form h2").textContent = "إضافة مكان";
                document.querySelector("label[for='placeType']").textContent = "نوع المكان:";
                document.querySelector("label[for='placeName']").textContent = "اسم المكان:";
                document.querySelector("label[for='buildingNumber']").textContent = "رقم المبنى:";
                document.querySelector("label[for='mobileNumber']").textContent = "رقم الجوال:";
                document.querySelector("label[for='placeImage']").textContent = "رفع صورة (اختياري):";
                document.querySelector("button").textContent = "إضافة مكان";
                document.querySelector(".places-list h2").textContent = "الأماكن الحقيقية في مصر:";
                document.querySelectorAll(".place-item h3")[0].textContent = "مطعم البرج";
                document.querySelectorAll(".place-item p")[0].textContent = "الموقع: 15 المهندسين، القاهرة";
                document.querySelectorAll(".place-item h3")[1].textContent = "كارفور سوبر ماركت";
                document.querySelectorAll(".place-item p")[2].textContent = "الموقع: 12 المعادي، القاهرة";
                document.querySelectorAll(".place-item h3")[2].textContent = "صالون السيد ت";
                document.querySelectorAll(".place-item p")[4].textContent = "الموقع: 20 الزمالك، القاهرة";
                document.querySelector("footer p").textContent = "تم التطوير بواسطة: مصطفى أحمد";
                document.querySelector("footer p + p").textContent = "رقم الاتصال: 01033022988";
            } else {
                document.querySelector("header h1").textContent = "Find Places in Egypt";
                document.querySelector(".place-form h2").textContent = "Add a Place";
                document.querySelector("label[for='placeType']").textContent = "Place Type:";
                document.querySelector("label[for='placeName']").textContent = "Place Name:";
                document.querySelector("label[for='buildingNumber']").textContent = "Building Number:";
                document.querySelector("label[for='mobileNumber']").textContent = "Mobile Number:";
                document.querySelector("label[for='placeImage']").textContent = "Upload Image (Optional):";
                document.querySelector("button").textContent = "Add Place";
                document.querySelector(".places-list h2").textContent = "Real Places in Egypt:";
                document.querySelectorAll(".place-item h3")[0].textContent = "El Borg Restaurant";
                document.querySelectorAll(".place-item p")[0].textContent = "Location: 15 El-Mohandeseen, Cairo";
                document.querySelectorAll(".place-item h3")[1].textContent = "Carrefour Supermarket";
                document.querySelectorAll(".place-item p")[2].textContent = "Location: 12 Maadi, Cairo";
                document.querySelectorAll(".place-item h3")[2].textContent = "Mr. T's Barbershop";
                document.querySelectorAll(".place-item p")[4].textContent = "Location: 20 Zamalek, Cairo";
                document.querySelector("footer p").textContent = "Developed by: Mostafa Ahmed";
                document.querySelector("footer p + p").textContent = "Contact: 01033022988";
            }
        }

        // Handle form submission
        document.getElementById("placeForm").addEventListener("submit", function (event) {
            event.preventDefault();
            alert("Place added successfully!");
        });
    </script>
</body>
</html>
