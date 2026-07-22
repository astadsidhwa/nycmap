# nycmap

NYC Interactive Food Map
A custom, interactive web map built to explore and track viral food spots, halal eateries, and neighborhood itineraries across New York City.

Features
Interactive Pins: Custom-mapped locations complete with details and tags.

Mobile-Friendly: Optimized to run smoothly directly in mobile web browsers (Safari/Chrome) for on-the-go navigation.

Local Persistence: Automatically saves custom additions and pin updates directly in your browser's local storage.


## AI Prompt Template for Adding Locations

To generate new location blocks for this map, paste the prompt below into any LLM (along with your list of places or desired food category/neighborhood).

### The Prompt to Copy/Paste:

> You are a data-formatting assistant for a custom Leaflet interactive map built in HTML/JavaScript. 
> 
> Your task is to take my input (either a specific list of places, or a type of food and region) and output **only** a valid JSON array of objects that matches the schema below. Do not include markdown code blocks around the entire output if possible, just raw JSON, or standard code block formatting.
> 
> ### Required JSON Schema for each item:
> ```json
> {
>   "id": "unique-kebab-case-name",
>   "name": "Exact Name of Place",
>   "category": "e.g., Halal, Burgers, Dessert",
>   "neighborhood": "e.g., Astoria, Lower East Side",
>   "lat": 40.7128,
>   "lng": -74.0060,
>   "description": "Short, engaging summary of what to try here."
> }
> ```
> 
> ### Rules:
> 1. Provide accurate geographic latitude and longitude coordinates (`lat`, `lng`) for each location.
> 2. Ensure IDs use lowercase letters and hyphens only.
> 3. Output *only* the JSON array so I can easily copy and paste it into my `defaultPlaces` array in the code.
> 
> Here is my input: [INSERT YOUR LIST OR FOOD TYPE/REGION HERE]
