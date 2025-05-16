<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Supply Chain Management</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 20px;
        }
        h1 {
            color: #2E86C1;
        }
        form {
            margin-bottom: 20px;
        }
        label {
            display: inline-block;
            width: 120px;
        }
        input[type="text"], input[type="number"] {
            width: 200px;
            padding: 5px;
            margin-bottom: 10px;
        }
        table {
            width: 100%;
            border-collapse: collapse;
            margin-top: 10px;
        }
        th, td {
            border: 1px solid #999;
            padding: 10px;
            text-align: left;
        }
        th {
            background-color: #D6EAF8;
        }
    </style>
</head>
<body>
    <h1>Supply Chain Management System</h1>

    <form id="supplyForm">
        <div>
            <label for="productName">Product Name:</label>
            <input type="text" id="productName" required>
        </div>
        <div>
            <label for="supplier">Supplier:</label>
            <input type="text" id="supplier" required>
        </div>
        <div>
            <label for="quantity">Quantity:</label>
            <input type="number" id="quantity" required>
        </div>
        <button type="submit">Add to Supply Chain</button>
    </form>

    <h2>Inventory Overview</h2>
    <table id="supplyTable">
        <thead>
            <tr>
                <th>Product</th>
                <th>Supplier</th>
                <th>Quantity</th>
            </tr>
        </thead>
        <tbody>
            <!-- Entries will appear here -->
        </tbody>
        
            const name = document.getElementById('productName').value.trim();
            const supplier = document.getElementById('supplier').value.trim();
            const quantity = document.getElementById('quantity').value;

            if (!name || !supplier || quantity <= 0) {
                alert("Please enter valid product information.");
                return;
            }

            const row = document.createElement('tr');

            row.innerHTML = `
                <td>${name}</td>
                <td>${supplier}</td>
                <td>${quantity}</td>
            `;

            tableBody.appendChild(row);

            form.reset();
        });
    </script>
</body>
</html>

    </table>
    
    <script>
        const form = document.getElementById('supplyForm');
        const tableBody = document.querySelector('#supplyTable tbody');

        form.addEventListener('submit', function(event) {
            event.preventDefault();
