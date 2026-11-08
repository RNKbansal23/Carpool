
# 🚗 Carpool - Ride Sharing & Peer-to-Peer Car Rentals

### One Platform. Two Solutions. Smarter Transportation.

**Carpool** is a web-based transportation platform designed to bring **carpooling and car rental services together in one application**.

The project focuses on making transportation affordable, accessible, and environmentally friendly by allowing users to share rides with people traveling along similar routes or rent vehicles for personal use.

A key idea behind Carpool is **peer-to-peer vehicle rental**: car owners can make their idle vehicles available for rent during specific dates, enabling others to use those vehicles while owners earn additional income.

The platform was developed as an academic project to explore full-stack web development, database integration, ride booking, user authentication, and automated email notifications.

### 🔗 Project Links

- **Live Demo:** https://dsn-2-bjda.onrender.com
- **GitHub Repository:** https://github.com/RNKbansal23/Carpool

---

## 📌 Table of Contents

1. [Project Overview](#-project-overview)
2. [Problem Statement](#-problem-statement)
3. [Our Solution](#-our-solution)
4. [Key Features](#-key-features)
5. [How It Works](#-how-it-works)
6. [Email Notifications and OTP](#-email-notifications-and-otp)
7. [Technology Stack](#-technology-stack)
8. [System Architecture](#-system-architecture)
9. [Project Structure](#-project-structure)
10. [Installation and Setup](#-installation-and-setup)
11. [Application Routes](#-application-routes)
12. [Security Considerations](#-security-considerations)
13. [Future Enhancements](#-future-enhancements)
14. [Learning Outcomes](#-learning-outcomes)
15. [Contributing](#-contributing)

---

## 📖 Project Overview

Carpool is a transportation platform that combines two important services:

### 1. Carpooling / Ride Sharing

Users traveling in the same direction can share a vehicle instead of booking separate transportation.

The platform allows passengers to provide their pickup location, destination, preferred departure date, time, and number of passengers.

Ride details are processed by the backend, and confirmation information is delivered through automated email notifications.

### 2. Car Rental / Vehicle Sharing

Users can browse vehicles available for rent and explore vehicle specifications and pricing.

The broader project concept introduces a peer-to-peer rental marketplace where individuals can list personal vehicles that are not currently in use.

For example:

> A car owner is traveling out of town for five days and has a vehicle sitting unused in their garage. Instead of leaving it idle, they can list the car on the platform and specify the dates during which it is available for rent.
>
> Another user who needs a vehicle during those dates can explore the listing and request to rent it.

This model encourages better vehicle utilization and gives owners an opportunity to generate income from unused assets.

---

## 🎯 Problem Statement

Transportation systems face several challenges:

- Rising transportation and fuel costs.
- Increasing traffic congestion in urban areas.
- Underutilization of privately owned vehicles.
- Limited affordable transportation options.
- Separate platforms for ride sharing and car rentals.
- Environmental impact caused by unnecessary vehicle usage.

Many people travel along similar routes every day but use different vehicles.

At the same time, privately owned cars frequently remain parked for long periods without being used.

### 💡 Our Solution

Carpool addresses these problems by combining ride sharing and car rental services into a unified transportation platform.

The proposed system enables:

- Passengers to request shared rides.
- Users to explore vehicles available for rent.
- Vehicle owners to list idle cars for specific dates.
- Automated booking-related email communication.
- Secure verification workflows as the platform develops.
- More efficient use of existing transportation resources.

The ultimate objective is to create a community-driven mobility ecosystem that makes transportation more economical and sustainable.

---

## ✨ Key Features

### 🚘 1. Carpooling and Ride Booking

The ride-booking module enables users to submit their travel requirements.

**Ride booking details include:**

- Passenger email address.
- Pickup location.
- Drop-off location.
- Departure date.
- Departure time.
- Number of passengers.

After submitting the form, the Flask backend processes the information and triggers an automated confirmation email.

**Current implementation:**
- Ride-booking form.
- Backend form processing.
- Email confirmation.
- Booking success page.

**Planned enhancements:**
- Dynamic driver matching.
- Driver-created ride listings.
- Available-seat management.
- Ride acceptance and cancellation.
- Shared fare calculation.

### 🚙 2. Car Rental System

The rental module allows users to browse featured vehicles using a web interface.

Vehicle cards display information such as:

- Vehicle brand and model.
- Manufacturing year.
- Seating capacity.
- Fuel type.
- Transmission.
- Fuel efficiency.
- Displayed rental price.
- Vehicle images.

Users can explore available options and navigate to additional rental pages.

The current implementation provides the rental browsing interface, while dynamic inventory and complete rental transaction processing remain future enhancements.

### 🏠 3. Peer-to-Peer Vehicle Rental

**Core product concept: Make money from cars sitting idle in your garage.**

Traditional car rental platforms generally depend on dedicated rental fleets.

Carpool introduces the concept of allowing everyday vehicle owners to rent their personal cars when they are not using them.

#### Vehicle Owner Workflow

1. Register or log in to the platform.
2. Choose to list a personal vehicle.
3. Enter vehicle details and rental pricing.
4. Upload vehicle images.
5. Specify the pickup location.
6. Set the available rental dates.
7. Receive rental requests from interested users.
8. Accept or reject requests.
9. Coordinate vehicle pickup and return.

#### Example

A vehicle owner can define:

| Field | Example |
|---|---|
| Vehicle | Hyundai i20 |
| Location | Jaipur |
| Availability Start | 10 December |
| Availability End | 15 December |
| Rental Price | ₹1,200/day |
| Availability | Available |

A renter searching for a vehicle between 12 and 14 December could request this car.

A completed availability engine would prevent overlapping reservations and automatically update the available rental dates.

**Development status:** Owner-managed listings, availability calendars, and rental conflict prevention represent the intended marketplace workflow and are not yet fully implemented in the repository.

### 👥 4. User Registration and Login

Carpool includes a basic authentication system for creating and accessing user accounts.

**Registration information:**
- Full name.
- Username.
- Email address.
- Password.

The application uses MongoDB to store user account records.

Flask sessions are used to maintain basic login state.

**Current implementation:**
- Registration form.
- Login form.
- MongoDB account storage.
- Session-based login.
- Logout functionality.

> Note: The authentication system is an academic prototype and requires additional security improvements before production use.

### 📧 5. Automated Email Notifications

Carpool integrates an automated email service using Python SMTP.

When a passenger submits a ride request, the backend generates a confirmation email containing information about the journey.

The email includes:

- Driver name.
- Departure date.
- Pickup time.
- Vehicle identifier.
- Pickup location.
- Drop-off location.
- Number of passengers.
- General instructions for the journey.

**Email technology:**
- Python `smtplib`.
- Gmail SMTP server.
- TLS-encrypted SMTP connection.
- MIME-based email formatting.

This feature demonstrates backend integration with an external communication service.

### 🔐 6. OTP-Based Verification — Planned

The proposed verification system is designed to improve trust between passengers, drivers, vehicle owners, and renters.

Potential verification use cases include:

- Email verification during registration.
- Driver identity confirmation.
- Rental request verification.
- Vehicle pickup authorization.
- Secure vehicle handover.

#### Proposed OTP Workflow

1. A user initiates a verification-sensitive action.
2. The backend generates a temporary OTP.
3. The OTP is sent to the authorized email address.
4. The recipient enters the OTP on the platform.
5. The backend validates the code and its expiration time.
6. The requested action is authorized after successful verification.

A production implementation should include OTP expiration, retry limits, secure storage, and single-use validation.

**Development status:** Automated booking emails are implemented. OTP generation and validation are planned and are not currently available as working backend functionality.

---

## 🔄 How It Works

### Workflow 1: Booking a Carpool Ride

```text
Passenger
    |
    v
Open Carpool Platform
    |
    v
Select "Book Ride"
    |
    v
Enter Journey Details
    |
    |-- Pickup Location
    |-- Destination
    |-- Departure Date
    |-- Departure Time
    |-- Passenger Count
    |-- Email Address
    |
    v
Submit Ride Request
    |
    v
Flask Backend Processes Form
    |
    v
SMTP Email Service
    |
    v
Ride Confirmation Email
    |
    v
Booking Success Page
```

The current prototype demonstrates ride-request processing and email delivery. Driver details in the confirmation are examples rather than the result of a live driver-matching system.

### Workflow 2: Renting a Vehicle

```text
User
    |
    v
Open Carpool Platform
    |
    v
Select "Rent Car"
    |
    v
Browse Vehicle Catalog
    |
    v
View Vehicle Specifications
    |
    v
Compare Displayed Prices
    |
    v
Select "Rent Now"
    |
    v
Navigate to Rental Page
```

The rental interface currently uses predefined vehicle listings.

### Workflow 3: Listing an Idle Vehicle — Product Vision

```text
Vehicle Owner
    |
    v
Register / Login
    |
    v
List Personal Vehicle
    |
    v
Enter Vehicle Details
    |
    v
Select Available Dates
    |
    v
Publish Rental Listing
    |
    v
Receive Rental Request
    |
    v
Review and Approve Booking
    |
    v
Email / OTP Verification
    |
    v
Vehicle Handover
    |
    v
Rental Completion
```

This workflow describes the planned peer-to-peer marketplace functionality.

---

## 📩 Email Notifications and OTP

### Implemented Email Confirmation Flow

The application uses the `emailer.py` module to send ride confirmation messages.

The Flask application invokes the email function after receiving a ride-booking request.

```python
send_email(
    receiver_email,
    driver_name,
    departure_date,
    pickup_time,
    car_id,
    pickup_point,
    dropoff_point,
    no_of_passengers
)
```

The email service uses Gmail SMTP:

```python
server = smtplib.SMTP("smtp.gmail.com", 587)
server.starttls()
server.login(SENDER_EMAIL, MAIL_PASS)
server.sendmail(
    SENDER_EMAIL,
    receiver_email,
    msg.as_string()
)
server.quit()
```

The sender credentials are read from environment variables:

```python
SENDER_EMAIL = os.getenv("CARPOOL_EMAIL")
MAIL_PASS = os.getenv("CARPOOL_PASSWORD")
```

### Example Booking Confirmation

```text
Subject: Your Carpool Ride is Confirmed!

Dear Customer,

Your carpool ride has been confirmed.

Ride Details:

Driver: Mr. Ramesh Kumar
Departure Date: 12 December
Pickup Time: 09:00 AM
Pickup Location: Jaipur
Drop-off Location: Ajmer
Passengers: 2

Please arrive at the pickup location
at least 5 minutes before departure.

Thank you for choosing Carpool!
```

The current implementation uses an example driver name and generates a vehicle identifier rather than retrieving an assigned driver from a database.

### Proposed Driver Notification System

In the extended platform, drivers and vehicle owners would receive automated notifications when:

- A passenger requests a seat.
- A vehicle rental request is created.
- A booking is accepted or cancelled.
- Vehicle pickup is scheduled.
- OTP verification is required.

---

## 🛠 Technology Stack

The following technologies are used in the current repository.

| Component | Technology |
|---|---|
| Programming Language | Python 3 |
| Backend Framework | Flask |
| Frontend | HTML5, CSS3, JavaScript |
| Template Engine | Jinja2 |
| Database | MongoDB |
| Database Driver | PyMongo |
| Authentication | Flask Sessions |
| Email Service | Python SMTP / Gmail SMTP |
| Application Server | Gunicorn |
| Containerization | Docker |
| Deployment | Render |

### Backend

**Flask** manages server-side routing, HTTP requests, HTML template rendering, user authentication, and ride-booking form processing.

### Database

**MongoDB** stores account information, with **PyMongo** providing the connection between the Flask backend and the database.

### Frontend

**HTML, CSS, JavaScript, and Jinja2** provide the application interface, page styling, navigation, forms, and server-rendered content.

### Email Integration

**Python SMTP** supports automated confirmation messages containing ride details.

---

## 🏗 System Architecture

```text
                  CLIENT / USER
                        |
                        v
             FRONTEND INTERFACE
           HTML | CSS | JavaScript
                        |
                        v
                 FLASK SERVER
                   (main.py)
                        |
          +-------------+-------------+
          |                           |
          v                           v
    USER MANAGEMENT             RIDE BOOKING
          |                           |
          v                           v
   mongo_functions.py             emailer.py
          |                           |
          v                           v
       MongoDB                   Gmail SMTP
          |                           |
          v                           v
   Account Records           Confirmation Email
```

### Architecture Explanation

**Frontend Layer**

Handles user interaction, registration forms, login forms, ride requests, and car rental browsing.

**Backend Layer**

Processes form submissions, handles routes, manages sessions, and coordinates database and email operations.

**Database Layer**

Stores account-related information through MongoDB.

**Communication Layer**

Sends confirmation messages through SMTP.

---

## 📂 Project Structure

```text
Carpool/
│
├── main.py
│   # Main Flask application
│
├── mongo_functions.py
│   # MongoDB connection and account operations
│
├── emailer.py
│   # Automated email service
│
├── requirements.txt
│   # Python project dependencies
│
├── Dockerfile
│   # Container configuration
│
├── templates/
│   ├── index.html
│   ├── login.html
│   ├── signup.html
│   ├── formPage.html
│   ├── book.html
│   ├── rent.html
│   ├── rent2.html
│   ├── success.html
│   └── contactUs.html
│
├── static/
│   ├── css/
│   ├── js/
│   ├── images/
│   └── assets/
│
├── .gitignore
│
└── README.md
```

---

## ⚙️ Installation and Setup

### Prerequisites

Ensure the following are available:

- Python 3.11
- pip
- MongoDB connection
- Git
- SMTP credentials for email testing

### Step 1: Clone the Repository

```bash
git clone https://github.com/RNKbansal23/Carpool.git
```

```bash
cd Carpool
```

### Step 2: Create a Virtual Environment

For Windows:

```bash
python -m venv venv
```

```bash
venv\Scripts\activate
```

For Linux/macOS:

```bash
python3 -m venv venv
```

```bash
source venv/bin/activate
```

### Step 3: Install Dependencies

```bash
pip install -r requirements.txt
```

The application uses the following Python packages:

```text
Flask==3.0.3
pymongo==3.11.0
dnspython==2.5.0
gunicorn==21.2.0
```

### Step 4: Configure Environment Variables

Configure the SMTP sender information.

```env
CARPOOL_EMAIL=your_email@gmail.com
CARPOOL_PASSWORD=your_email_app_password
```

Use environment variables or another secure secrets-management method.

The existing MongoDB connection string and Flask secret are hard-coded in the source and should be migrated to environment variables before deployment.

A future configuration could use:

```env
MONGO_URI=your_mongodb_connection_string
FLASK_SECRET_KEY=your_secure_secret
CARPOOL_EMAIL=your_email@gmail.com
CARPOOL_PASSWORD=your_email_app_password
```

The backend must be updated to read `MONGO_URI` and `FLASK_SECRET_KEY` before those variables will work.

**Never commit real passwords, database credentials, or API keys to GitHub.**

### Step 5: Start the Flask Application

```bash
flask --app main run --debug
```

### Step 6: Open the Application

Visit:

```text
http://127.0.0.1:5000
```

**Note:** The current `main.py` contains an incorrect Python entry-point guard. The Flask CLI command above avoids that issue. A functioning MongoDB connection is also required for account-related operations.

---

## 🌐 Application Routes

| Method | Endpoint | Description |
|---|---|---|
| GET | `/` | Home page |
| GET, POST | `/signup` | User registration |
| GET, POST | `/login` | User login |
| GET | `/logout` | User logout |
| GET | `/bookride` | Ride-booking page |
| POST | `/submit_form` | Process ride request and send confirmation |
| GET | `/rentcar` | Car rental catalog |
| GET | `/rent2` | Additional rental page |
| GET | `/contact` | Contact page |

The application currently uses server-rendered routes and HTML forms rather than a separate REST API.

---

## 🔒 Security Considerations

The existing implementation is an academic prototype. Several improvements are necessary before handling real customer data or vehicle transactions.

### Current Limitations

- Account passwords are currently stored without secure hashing.
- The MongoDB connection string contains hard-coded credentials.
- Flask uses a hard-coded application secret.
- OTP verification has not yet been implemented.
- Rental availability is not maintained in a dynamic booking database.
- Rental listings are primarily static UI content.
- Real-time driver matching is not implemented.
- Payment gateway integration is not implemented.
- Driver identity verification requires further development.

### Recommended Improvements

- Use secure password hashing.
- Move credentials to environment variables.
- Rotate exposed database credentials and application secrets.
- Implement role-based authorization.
- Add secure OTP verification.
- Validate all user inputs.
- Implement booking persistence.
- Prevent overlapping rental bookings.
- Protect sensitive account and rental information.
- Add automated backend tests.

---

## 🚀 Future Enhancements

### 1. Dynamic Driver Matching

Match passengers with drivers traveling along compatible routes.

### 2. Vehicle Owner Dashboard

Allow owners to manage their vehicle listings, availability dates, pricing, and booking requests.

### 3. Availability Calendar

Enable vehicle owners to define exact rental windows and automatically prevent double bookings.

### 4. OTP Verification

Verify email addresses, driver identities, booking requests, and vehicle handovers.

### 5. Payment Gateway Integration

Integrate payment services such as Razorpay or Stripe to support rental payments and shared travel costs.

### 6. Live Location Integration

Use mapping services to improve pickup selection, route matching, and navigation.

### 7. Booking History

Allow users to access past rides, rental requests, and booking information.

### 8. Reviews and Ratings

Introduce feedback mechanisms for drivers, vehicle owners, and renters.

### 9. Real-Time Notifications

Notify users about booking confirmations, cancellations, pickup reminders, and status updates.

### 10. Improved Authentication and Security

Introduce stronger authentication, secure session management, authorization controls, and verified vehicle ownership.

---

## 📚 Learning Outcomes

Developing Carpool provided practical exposure to several important software development concepts.

### Backend Development

- Building web applications using Python and Flask.
- Implementing routes and processing HTTP requests.
- Handling user-submitted forms.
- Integrating backend services.

### Database Management

- Connecting Flask applications to MongoDB.
- Performing basic database operations.
- Managing user account records.

### Authentication

- Implementing registration and login functionality.
- Using sessions to track authentication state.
- Understanding the importance of secure credential management.

### Email Automation

- Integrating Python SMTP.
- Generating automated ride confirmation emails.
- Passing booking information between backend modules.

### Frontend Development

- Building responsive web interfaces.
- Creating registration, login, and booking forms.
- Designing a vehicle rental catalog.

### Software Architecture

- Separating frontend templates, backend routes, database operations, and communication services.
- Understanding how multiple transportation services can be combined into a single platform.
- Designing workflows for a peer-to-peer marketplace.

---

## 🌱 Project Vision

Carpool is designed around the idea that transportation resources should be used more efficiently.

Instead of allowing privately owned vehicles to remain unused, the platform envisions a system where vehicle owners can share their cars with people who need temporary transportation.

Similarly, passengers traveling along compatible routes could reduce individual travel costs by sharing journeys.

By combining these ideas, Carpool aims to create a more accessible, affordable, and community-oriented transportation experience.

---

## 🤝 Contributing

Contributions and suggestions are welcome.

To contribute:

1. Fork the repository.
2. Create a new feature branch.
3. Make your changes.
4. Test your implementation.
5. Commit your changes.
6. Open a pull request.

```bash
git checkout -b feature/new-feature
git add .
git commit -m "Add new feature"
git push origin feature/new-feature
```

---

## 📄 License

A license file has not yet been added to this repository.

A license such as MIT may be added in the future if the project is intended for open-source distribution.

---

## 👨‍💻 Project Repository

**GitHub:** https://github.com/RNKbansal23/Carpool

**Live Application:** https://dsn-2-bjda.onrender.com

---

### 🚗 Carpool — Share the Journey. Rent the Possibilities. Make Every Car Count.
