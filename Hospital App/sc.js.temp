let bookings = []; // store booking history

// Login Logic
document.getElementById("login-btn").onclick = function () {
    let user = document.getElementById("username").value;
    let pass = document.getElementById("password").value;

    if (user === "admin" && pass === "1234") {
        document.getElementById("login-section").style.display = "none";
        document.getElementById("appointment-section").style.display = "block";
    } else {
        document.getElementById("login-msg").innerText = "Invalid Credentials!";
    }
};

// Booking Logic with Validation
document.getElementById("book-btn").onclick = function () {
    let doctor = document.getElementById("doctor").value;
    let date = document.getElementById("date").value;
    let time = document.getElementById("time").value;

    // Validation: empty fields
    if (!date || !time) {
        document.getElementById("status").innerText = "Please select date and time!";
        return;
    }

    // Validation: prevent duplicate booking
    let exists = bookings.find(b => b.date === date && b.time === time);

    if (exists) {
        document.getElementById("status").innerText =
            "❌ Slot already booked! Choose another time.";
        return;
    }

    // Save booking
    let booking = { doctor, date, time };
    bookings.push(booking);

    document.getElementById("status").innerText =
        "✅ Appointment booked with " + doctor + " on " + date + " at " + time;

    showHistory();
};

// Show Booking History
function showHistory() {
    let historyDiv = document.getElementById("history");
    historyDiv.innerHTML = "<h3>Booking History</h3>";

    bookings.forEach((b, index) => {
        historyDiv.innerHTML +=
            `<p>${index + 1}. ${b.doctor} - ${b.date} - ${b.time}</p>`;
    });
}

// Logout Logic
document.getElementById("logout-btn").onclick = function () {
    document.getElementById("appointment-section").style.display = "none";
    document.getElementById("login-section").style.display = "block";
};