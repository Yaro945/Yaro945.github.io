document.addEventListener('DOMContentLoaded', (event) => {
    const map = L.map('map').setView([51.505, -0.09], 13); // Default location (London)

    L.tileLayer('https://{s}.tile.openstreetmap.org/{z}/{x}/{y}.png', {
        attribution: '&copy; <a href="https://www.openstreetmap.org/copyright">OpenStreetMap</a> contributors'
    }).addTo(map);

    // Try HTML5 geolocation
    if (navigator.geolocation) {
        navigator.geolocation.getCurrentPosition(
            (position) => {
                const pos = [position.coords.latitude, position.coords.longitude];

                map.setView(pos, 15);
                L.marker(pos).addTo(map)
                    .bindPopup('You are here!')
                    .openPopup();
            },
            () => {
                alert("Unable to retrieve your location.");
            }
        );
    } else {
        alert("Geolocation is not supported by this browser.");
    }
});
