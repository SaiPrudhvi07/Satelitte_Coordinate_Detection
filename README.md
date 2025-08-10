# Satelitte_Coordinate_Detection
# Algorithm
1. Fetch ISS Position
  The application retrieves the current position of the ISS using the Open Notify API (http://api.open-notify.org/iss-now.json).
  The API provides the latitude and longitude of the ISS, which are stored for comparison with your location.

2. Get Sunrise and Sunset Data
  The application fetches sunrise and sunset times using the Sunrise-Sunset API (https://api.sunrise-sunset.org/json).
  Based on your latitude and longitude, the API returns the time of sunrise and sunset in UTC.
  These times are extracted and converted into hour values for comparison with the current time.

3. Check ISS Visibility
  The application determines whether the ISS is within a visible range of your location. This is done by checking if the ISS’s current latitude and longitude are within ±5 degrees of your location's latitude and longitude.
  The visibility also depends on whether the current time is between sunset and sunrise (i.e., during the night).
  If both conditions are met (proximity and nighttime), the ISS is considered visible.

4. Visual Feedback with Tkinter
  The application creates a graphical user interface (GUI) using Tkinter.
  If the ISS is visible, the background of the window turns green, and the text displays "CAN SEE ISS."
  If the ISS is not visible, the background turns red, and the text displays "CANNOT SEE ISS."
  The position of the ISS is checked every second using the window.after() method in Tkinter, ensuring real-time updates.

# APIs Used
  Open Notify API: Provides real-time data on the current position of the ISS.
  Sunrise-Sunset API: Provides the sunrise and sunset times for a given location.
