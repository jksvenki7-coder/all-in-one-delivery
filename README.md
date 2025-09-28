# all-in-one-delivery
fresh and fast delivery service
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1" />
<title>JKS Delivery Service</title>
<link rel="stylesheet" href="style.css" />
</head>
<body>
<nav>
    <button onclick="showPage('home')">Home</button>
    <button onclick="openCamera()">Camera</button>
    <button onclick="openGoogleMaps()">Google Maps</button>
    <button onclick="showPage('orders')">Orders</button>
</nav>
<main>
    <section id="home">
        <h2>Welcome to JKS Delivery Service</h2>
        <div class="categories">
            <button onclick="openFolder('groceries')">Groceries</button>
            <button onclick="openFolder('food')">Food</button>
            <button onclick="openFolder('pharmacy')">Pharmacy</button>
        </div>
        <div id="folder-content"></div>
    </section>

    <section id="orders" style="display:none;">
        <h2>Your Orders</h2>
        <div id="orders-list">No orders yet.</div>
    </section>
</main>
<script src="script.js"></script>
</body>
</html>body {
    font-family: Arial, sans-serif;
    background: #f5faff;
    color: #222;
    margin: 0;
    padding: 0;
}

nav {
    background: #e0f2ff;
    padding: 12px;
    display: flex;
    gap: 10px;
    justify-content: center;
}

nav button {
    background: #009dff;
    color: white;
    border: none;
    padding: 10px 18px;
    border-radius: 6px;
    cursor: pointer;
}

nav button:hover {
    background: #0266a3;
}

main {
    padding: 24px;
}

.categories {
    margin: 20px 0;
    display: flex;
    flex-wrap: wrap;
    gap: 12px;
    justify-content: center;
}

.categories button {
    background: #38b6ff;
    border: none;
    color: white;
    padding: 12px 20px;
    border-radius: 8px;
    cursor: pointer;
}

.categories button:hover {
    background: #0266a3;
}

#folder-content {
    margin-top: 20px;
    max-width: 960px;
    margin-left: auto;
    margin-right: auto;
}

.images-grid {
    display: grid;
    grid-template-columns: repeat(auto-fill,minmax(150px,1fr));
    gap: 15px;
    margin-bottom: 24px;
}

.images-grid img {
    width: 100%;
    border-radius: 8px;
    border: 1px solid #cde7ff;
    box-shadow: 0 0 6px #b6e0ff;
}

#folder-content form {
    background: white;
    border: 1px solid #b8e1ff;
    border-radius: 8px;
    padding: 22px;
    max-width: 400px;
    margin: 0 auto 30px auto;
}

#folder-content form label {
    display: block;
    margin-top: 12px;
}

#folder-content form input,
#folder-content form textarea {
    width: 100%;
    padding: 8px;
    margin-top: 4px;
    border-radius: 4px;
    border: 1px solid #d9d9d9;
}

#folder-content form button {
    margin-top: 18px;
    background: #009dff;
    color: white;
    border: none;
    padding: 10px 15px;
    border-radius: 5px;
    cursor: pointer;
}
const whatsappNumber = "918977143043";

const foldersData = {
    groceries: {
        title: "Groceries",
        images: [
            "https://via.placeholder.com/150?text=Groceries+1",
            "https://via.placeholder.com/150?text=Groceries+2",
            "https://via.placeholder.com/150?text=Groceries+3",
            "https://via.placeholder.com/150?text=Groceries+4",
            "https://via.placeholder.com/150?text=Groceries+5",
            "https://via.placeholder.com/150?text=Groceries+6",
            "https://via.placeholder.com/150?text=Groceries+7",
            "https://via.placeholder.com/150?text=Groceries+8",
            "https://via.placeholder.com/150?text=Groceries+9",
            "https://via.placeholder.com/150?text=Groceries+10"
        ],
        placeholderItem: "e.g. Rice, Sugar"
    },
    food: {
        title: "Food",
        images: [
            "https://via.placeholder.com/150?text=Food+1",
            "https://via.placeholder.com/150?text=Food+2",
            "https://via.placeholder.com/150?text=Food+3",
            "https://via.placeholder.com/150?text=Food+4",
            "https://via.placeholder.com/150?text=Food+5",
            "https://via.placeholder.com/150?text=Food+6",
            "https://via.placeholder.com/150?text=Food+7",
            "https://via.placeholder.com/150?text=Food+8",
            "https://via.placeholder.com/150?text=Food+9",
            "https://via.placeholder.com/150?text=Food+10"
        ],
        placeholderItem: "e.g. Chicken, Biryani"
    },
    pharmacy: {
        title: "Pharmacy",
        images: [
            "https://via.placeholder.com/150?text=Pharmacy+1",
            "https://via.placeholder.com/150?text=Pharmacy+2",
            "https://via.placeholder.com/150?text=Pharmacy+3",
            "https://via.placeholder.com/150?text=Pharmacy+4",
            "https://via.placeholder.com/150?text=Pharmacy+5",
            "https://via.placeholder.com/150?text=Pharmacy+6",
            "https://via.placeholder.com/150?text=Pharmacy+7",
            "https://via.placeholder.com/150?text=Pharmacy+8",
            "https://via.placeholder.com/150?text=Pharmacy+9",
            "https://via.placeholder.com/150?text=Pharmacy+10"
        ],
        placeholderItem: "e.g. Medicine, Syrup"
    }
};

function showPage(page) {
    document.getElementById('home').style.display = page === 'home' ? 'block' : 'none';
    document.getElementById('orders').style.display = page === 'orders' ? 'block' : 'none';
    if (page !== 'home') {
        document.getElementById('folder-content').innerHTML = '';
    }
}

function openCamera() {
    const cameraInput = document.createElement('input');
    cameraInput.type = 'file';
    cameraInput.accept = 'image/*';
    cameraInput.capture = 'environment';
    cameraInput.style.display = 'none';
    cameraInput.onchange = () => {
        alert('Image captured. Feature to save or upload coming soon!');
    };
    document.body.appendChild(cameraInput);
    cameraInput.click();
    document.body.removeChild(cameraInput);
}

function openGoogleMaps() {
    window.open("https://maps.google.com", "_blank");
}

function openFolder(folderName) {
    const folder = foldersData[folderName];
    if (!folder) return;

    const folderContent = document.getElementById('folder-content');
    let imagesHtml = '<div class="images-grid">';
    folder.images.forEach(src => {
        imagesHtml += `<img src="${src}" alt="${folder.title} image" />`;
    });
    imagesHtml += '</div>';

    const formHtml = `
    <form id="order-form">
        <h3>${folder.title} Order</h3>
        <label>Name:
            <input type="text" name="name" required />
        </label>
        <label>Phone Number:
            <input type="tel" name="phone" required pattern="\\d{10}" placeholder="10-digit number" />
        </label>
        <label>Order Item:
            <input type="text" name="item" required placeholder="${folder.placeholderItem}" />
        </label>
        <label>Delivery Address:
            <textarea name="address" required></textarea>
        </label>
        <button type="submit">Order via WhatsApp</button>
    </form>`;

    folderContent.innerHTML = imagesHtml + formHtml;

    document.getElementById('order-form').onsubmit = function(event) {
        event.preventDefault();
        sendOrderViaWhatsApp(folderName, this);
    };
}

function sendOrderViaWhatsApp(folderName, form) {
    const name = form.name.value.trim();
    const phone = form.phone.value.trim();
    const item = form.item.value.trim();
    const address = form.address.value.trim();
    const message = `Order Category: ${folderName}\nName: ${name}\nPhone: ${phone}\nItem: ${item}\nAddress: ${address}`;
    const encodedMessage = encodeURIComponent(message);
    window.open(`https://wa.me/${whatsappNumber}?text=${encodedMessage}`, '_blank');
}
#folder-content form button:hover {
    background: #0266a3;
}
