# Customisable and Interactive NYC Map

NYC Interactive Food Map
A custom, interactive web map built to explore and track viral food spots, halal eateries, and neighborhood itineraries across New York City.

Features
Interactive Pins: Custom-mapped locations complete with details and tags.

Mobile-Friendly: Optimized to run smoothly directly in mobile web browsers (Safari/Chrome) for on-the-go navigation.

Local Persistence: Automatically saves custom additions and pin updates directly in your browser's local storage.

## AI Prompt Template for Adding Locations

To generate new location blocks for this map, paste the prompt below into any LLM (along with your list of places or desired food category/region).

### The Prompt to Copy/Paste:

> You are an expert data-research and formatting assistant for a custom interactive Leaflet map built in HTML/JavaScript. 
> 
> Your goal is to process my input and perform an all-in-one, end-to-end lookup to output **only** a valid JSON array of fully populated objects matching the schema below. You must handle all necessary research in a single pass without needing follow-up prompts or manual data entry from me.
> 
> ### Research & Processing Guidelines:
> 1. **If provided a simple list of place names:**
>    - Use web search to look up each venue's exact real-world business details.
>    - Retrieve the verified full street address, borough/neighborhood, and precise latitude & longitude coordinates.
>    - Determine the current operational status, price level (`$`, `$$`, `$$$`, `$$$$`), and whether the establishment serves Halal food (`isHalal`: `true`/`false`).
>    - Research signature dishes, viral items, or highlights to craft a concise, useful summary for the `notes` field.
> 
> 2. **If provided a food type, cuisine, or region (e.g., "Best Halal spots in Astoria"):**
>    - Use web search to curate top-rated, currently trending, or iconic spots matching the criteria.
>    - Fully research each selected venue across all schema fields listed below.
> 
> ### Required JSON Schema for each item:
> ```json
> {
>   "id": "unique-kebab-case-name",
>   "name": "Exact Name of Place",
>   "emoji": "🌮",
>   "category": "e.g., street-food, fine-dining, cafe, bakery, casual-dining",
>   "day": 1,
>   "isHalal": true,
>   "address": "Full Street Address, City, State ZIP",
>   "coordinates": [40.7128, -74.0060],
>   "region": "e.g., Brooklyn, Queens, Manhattan",
>   "notes": "Short, engaging summary highlighting signature dishes or viral items.",
>   "priceLevel": "$$"
> }
> ```
> 
> ### Strict Execution Rules:
> - **Be Thorough:** Do not leave any field empty or use placeholders (like `null`, `TBD`, or `0.0`). Every single field must be researched and filled out.
> - **Coordinates:** Must be formatted strictly as a two-item array of floats `[latitude, longitude]` with high geographic accuracy.
> - **IDs:** Use lowercase letters and hyphens only (e.g., `"ayat-palestinian"`).
> - **Day Field:** Assign a logical integer (`1`, `2`, `3`, etc.) if organizing an itinerary, or default to `1`.
> - **Output Format:** Return **ONLY** the raw JSON array (or formatted inside a single standard markdown code block) with zero conversational filler before or after.
> 
> Here is my input: [INSERT YOUR LIST OF NAMES OR FOOD TYPE/REGION HERE]
