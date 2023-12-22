<!DOCTYPE html>
<html>
<head>
    <title>Zoho Token Retrieval</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #f4f4f4;
            margin: 0;
            padding: 0;
        }

        h1 {
            background-color: #007BFF;
            color: #fff;
            padding: 10px;
            text-align: center;
        }

        .container {
            max-width: 400px;
            margin: 0 auto;
            background-color: #fff;
            padding: 70px;
            border-radius: 5px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
        }

        label {
            display: block;
            font-weight: bold;
            margin-bottom: 5px;
        }

        input[type="text"] {
            width: 100%;
            padding: 10px;
            margin-bottom: 10px;
            border: 1px solid #ccc;
            border-radius: 3px;
        }

        input[type="submit"] {
            background-color: #007BFF;
            color: #fff;
            padding: 10px 20px;
            border: none;
            border-radius: 3px;
            cursor: pointer;
            float: left; /* Float the "Get Tokens" button to the left */
        }

        input[type="submit"]:hover {
            background-color: #0056b3;
        }

        /* Style for the "Reset ID and Secret" button */
        #reset_button {
            background-color: #007BFF;
            color: #fff;
            padding: 10px 20px;
            border: none;
            border-radius: 3px;
            cursor: pointer;
            float: left; /* Float the "Reset ID and Secret" button to the left */
            margin-left: 10px; /* Add some spacing between the two buttons */
        }

        #reset_button:hover {
            background-color: #0056b3;
        }

        .error-message {
            color: red;
            font-weight: bold;
            text-align: center;
            margin-top: 10px;
        }

        .token-container {
            margin-top: 20px;
            padding: 50px;
            background-color: #f4f4f4;
            border-radius: 5px;
            box-shadow: 0 0 5px rgba(0, 0, 0, 0.2);
        }

        .token-text {
            width: 100%;
            height: 100px;
            padding: 10px;
            border: 1px solid #ccc;
            border-radius: 3px;
        }
    </style>
    <script>
        function showError(errorMessage) {
            alert(errorMessage);
        }

        window.onload = function() {
            // Check if client ID and client secret are stored in local storage
            if (localStorage.getItem("client_id") && localStorage.getItem("client_secret")) {
                document.getElementById("client_id").value = localStorage.getItem("client_id");
                document.getElementById("client_secret").value = localStorage.getItem("client_secret");
            }

            // Reset button action
            document.getElementById("reset_button").addEventListener("click", function() {
                localStorage.removeItem("client_id");
                localStorage.removeItem("client_secret");
                document.getElementById("client_id").value = "";
                document.getElementById("client_secret").value = "";
            });
        }
    </script>
</head>
<body>
    <h1>Zoho Token Retrieval</h1>

    <div class="container">
        <?php
        if ($_SERVER["REQUEST_METHOD"] == "POST") {
            $client_id = $_POST["client_id"];
            $client_secret = $_POST["client_secret"];
            $code = $_POST["code"];

            // Store client ID and client secret in local storage
            if ($client_id && $client_secret) {
                echo "<script>localStorage.setItem('client_id', '$client_id');</script>";
                echo "<script>localStorage.setItem('client_secret', '$client_secret');</script>";
            }

            // Command 1: Getting Access and Refresh Tokens
            $data = array(
                "grant_type" => "authorization_code",
                "client_id" => $client_id,
                "client_secret" => $client_secret,
                "code" => $code
            );

            $token_url = "https://accounts.zoho.com/oauth/v2/token";
            $ch = curl_init($token_url);

            curl_setopt($ch, CURLOPT_RETURNTRANSFER, true);
            curl_setopt($ch, CURLOPT_POST, true);
            curl_setopt($ch, CURLOPT_POSTFIELDS, http_build_query($data));

            $response = curl_exec($ch);

            if ($response === false) {
                echo "<div class='error-message'>Error: Unable to connect to the token endpoint.</div>";
            } else {
                $token_data = json_decode($response, true);

                if (isset($token_data["access_token"]) && isset($token_data["refresh_token"])) {
                    $access_token = $token_data["access_token"];
                    $refresh_token = $token_data["refresh_token"];

                    echo "<div class='token-container'>";
                    echo "<p><strong>Access Token:</strong></p>";
                    echo "<textarea readonly class='token-text'>" . $access_token . "</textarea>";
                    echo "<p><strong>Refresh Token:</strong></p>";
                    echo "<textarea readonly class='token-text'>" . $refresh_token . "</textarea>";
                    echo "</div>";
                } else {
                    echo "<div class='error-message'>Error: Invalid response from the token endpoint.</div>";
                }
            }

            curl_close($ch);
        }
        ?>
        <form method="post" action="">
            <label for="client_id">Client ID:</label>
            <input type="text" id="client_id" name="client_id" required><br>
            <label for="client_secret">Client Secret:</label>
            <input type="text" id="client_secret" name="client_secret" required><br>
            <label for="code">Authorization Code:</label>
            <input type="text" name="code" required><br>

            <!-- Container for both buttons -->
            <div>
                <input type="submit" value="Get Tokens">
                <button id="reset_button">Reset ID and Secret</button>
            </div>
        </form>
    </div>
</body>
</html>
