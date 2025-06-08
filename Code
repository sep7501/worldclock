$w.onReady(function () {
    const timeZones = [
        "UTC",
        "America/New_York",
        "America/Chicago",
        "America/Denver",
        "America/Los_Angeles",
        "Europe/London",
        "Europe/Paris",
        "Europe/Berlin",
        "Europe/Moscow",
        "Asia/Tokyo",
        "Asia/Shanghai",
        "Asia/Kolkata",
        "Asia/Dubai",
        "Australia/Sydney",
        "Pacific/Auckland"
    ];

    const zoneData = timeZones.map(zone => {
        return {
            timezone: zone,
            time: getTimeInZone(zone)
        };
    });

    $w("#repeater1").data = zoneData;

    $w("#repeater1").onItemReady(($item, itemData, index) => {
        $item("#timezoneText").text = itemData.timezone;
        $item("#timeText").text = itemData.time;
    });

    // Update every minute
    setInterval(() => {
        const updatedData = timeZones.map(zone => {
            return {
                timezone: zone,
                time: getTimeInZone(zone)
            };
        });
        $w("#repeater1").data = updatedData;
    }, 60000);
});

// Helper to get current time in a specific timezone
function getTimeInZone(zone) {
    return new Date().toLocaleString("en-US", {
        timeZone: zone,
        hour: '2-digit',
        minute: '2-digit',
        second: '2-digit',
        hour12: false
    });
}
