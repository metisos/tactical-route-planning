# Metis OS Tactical Route Planning API
The Metis OS Tactical Route Planning API provides alternative route suggestions for users traveling between locations with optional waypoints. The API can be integrated into a wide range of applications, including geospatial systems and tactical platforms.
Base URL
text
Copy code
https://www.metisos.co/api/route-planning/

HTTP Request
Method: GET
The API uses a GET request to retrieve the route plan.
Endpoint
text
Copy code
/api/route-planning/

Parameters
Parameter
Type
Required
Description
origin
String
Yes
The starting point for the route (e.g., New York).
destination
String
Yes
The endpoint of the route (e.g., Boston).
waypoints
String
No
Optional waypoints along the route (e.g., Philadelphia).

Example Request
text
Copy code
https://www.metisos.co/api/route-planning/?origin=New+York&destination=Boston&waypoints=Philadelphia

Response Format
The API returns a JSON object with detailed route information, including estimated time, distance, and a breakdown of the route segments.
Example Response
json
Copy code
{
  "origin": "New York",
  "destination": "Boston",
  "waypoints": ["Philadelphia"],
  "route": {
    "total_distance": "215 miles",
    "estimated_time": "4 hours",
    "segments": [
      {
        "start": "New York",
        "end": "Philadelphia",
        "distance": "95 miles",
        "estimated_time": "1.5 hours"
      },
      {
        "start": "Philadelphia",
        "end": "Boston",
        "distance": "120 miles",
        "estimated_time": "2.5 hours"
      }
    ]
  }
}

Error Handling
The API returns the following error codes:
Status Code
Description
400
Invalid parameters or missing fields
404
Route not found
500
Internal server error

Example Error Response
json
Copy code
{
  "error": "Invalid origin or destination",
  "status_code": 400
}

Usage Limits
The API is rate-limited to prevent abuse. Contact Metis OS for more details on rate limits and API access.

