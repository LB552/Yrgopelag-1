# Feedback
## Styling
calendar.css:1-6 - The date layout doesn't match with January 2026 in reality. Consider adding three white spaces on the first week row, so as to have January 1st be a thursday. This could be achieved with a for loop in 

styles.css:3 - "padding: 0;" doesn't achieve anything and can be removed entirely.

form.php:45&62 - “Adventure” and “Water” use different tags, h4 and h3 respectively. For consistency, use either or. The recommended tag is h4, since this text is lower in hierarchy than "Select features" above, which uses h3 tags.

## Semantics
feature-info.php - You use h2 both for the top text on line 2 and for the feature cards. Syling-wise this causes no issues, since you apply styling to the top text by class. However, search engines and screen readers ignore CSS and rely on correct semantic heading levels.

## Structure
feature-info.php:4-25 - DRY: You code similar structure multiple times. Avoid repetition using dynamic HTML generation.

form.php:46-65 - DRY: You code similar structure multiple times. Avoid repetition using dynamic HTML generation.

footer.php:5-9 - DRY: You code similar structure multiple times. Avoid repetition using dynamic HTML generation.

# Yrgopelag

## Project description

This project is a hotel booking web application built around a fictional island and hotel concept.
The chosen concept is a tented camp on a volcano island.
The website allows visitors to view room availability and book one of three single rooms—budget, standard, or luxury.
The user can also select optional features and a package deal.

The project operates together with a Central Bank service, which means the booking flow is the following:

- The user checks the dates availability and select a tent type, dates of departure and arrival, plus optional features.
- The UI displays a total amount and possible discount.
- The user enters the total amount together with the API_KEY and creates a transfercode via the Central Bank.
- If a valid transfercode is created, the user can go back to the UI and use it to proceed with the booking.
- If the booking is successful, a receipt is displayed.

Validation is in place to ensure that the user can actually book.

## Languages and project structure

Backend & Rendering: PHP (server-side rendering and business logic)

Database: SQL (booking data, rooms, features, guest stays)

Styling: CSS

Interactivity: Minimal JavaScript for UI and price display

API Communication: Guzzle HTTP client

Configuration: Environment variables for sensitive credentials

## To run the project locally

1. Clone the repository
2. Install PHP dependencies using Composer:

   ```bash
   composer install

   ```

3. Create a .env file in the project root and add your API key and database configuration

4. Run the following command to create or reset the database:
   php backend/reset-database.php

   If successful you will get the following terminal message:
   ✅ Database reset successfully: backend/database/database.db

5. Start a localhost in the terminal: php -S localhost:8000;

6. Open the site in your browser

# Limitations and future improvements

- The project is designed for desktop use only.
- The UI is one page only. In the future I could expand it and include proper navigation, routing and more data.
- The confirmation for the transfercode and receipt is very minimalistic and not styled.
- the booking flow could be improved to be more user friendly, for example the total amount could be sent directly to the central bank instead of being manually added by the user.
