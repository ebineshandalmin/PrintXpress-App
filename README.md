🖨️ PrintXpress – Custom Printing & Merchandise Ordering App (Android)

📌 Overview

Android application for ordering custom‑printed products (banners, posters, business cards, flyers, stickers, T‑shirts, mugs)
Built with Java and Firebase (Authentication, Realtime Database, Storage)
Real‑time price calculation, design uploads, order history, notifications, public forum

👤 User Features

Register / Login with email or phone number
Password reset via email
Profile management – view/edit personal details
Browse services from dashboard (6 service cards)
View active order progress and offers slider
Place orders for multiple product categories
Upload design files or provide text details
Real‑time price breakdown (subtotal, finishing, delivery)
View order history with status
Receive notifications (order updates, admin replies)
Post comments in public forum, receive admin replies

🛍️ Product Categories & Customization

Product	& Key Options
Banner - Size (feet), quantity, material (vinyl/flex/mesh), finishing (eyelets, pole pockets, hemming), category (Event/Business/Advertising), delivery/pickup
Poster - Size (feet), quantity, paper type, print quality (Standard/Premium/Ultra HD), add‑ons (lamination, frame, mount board, waterproof), category
Flyer	- Quantity, size (A5/A4/A6/DL), paper type, print quality, orientation, sides (single/double), finishing (lamination, folding, UV coating, waterproof), design upload or text details
Business Card	- Quantity, card quality (Standard/Premium/Luxury), size (standard/square), paper type, design upload or text entry
Sticker	- Format (die‑cut/kiss‑cut/sheet), shape (circle/square/rectangle/custom), quantity, size, material, design upload
Merchandise	- T‑Shirt or Mug, quantity, material, size (S‑XXL), color, design upload

📦 Order Management

Order data stored in Firebase Orders/{userId} node
Each order includes: product name, quantity, size, paper type, print quality, finishing options, delivery type, address, phone, total price, timestamp, status (Pending by default)
Order history displayed in HistoryActivity (recycler view)
Active booking preview on dashboard (hardcoded demo)

💬 Public Forum

Users can post comments in PublicForumActivity
Admin (hardcoded email admin@gmail.com) can long‑press a comment to reply
Replies appear below comment with “OFFICIAL ADMIN” badge
Notifications sent to comment author when admin replies
Search comments, filter chips (Latest, Popular, Official, My Posts) – UI only

🔔 Notifications

Firebase Notification node stores notifications
Notifications for: order status updates, admin replies
Displayed in NotificationActivity with title, message, timestamp, icon
Notifications can target a specific user or “all”

👤 Profile

View profile picture, name, email, phone, address
Edit profile details (name, phone, address) – UI available but edit logic not fully implemented
Logout option
Bottom navigation to Dashboard, Orders, Forum, Profile

🛠️ Tech Stack

Language – Java
UI – XML, Material Design (CardView, TextInputLayout, BottomNavigationView, ViewPager2)
Backend – Firebase Authentication, Firebase Realtime Database, Firebase Storage
Image Cropping – com.canhub.cropper (CropImage)
Image Loading – Glide (not explicitly imported but likely used)

📁 Key Files (Selected)

Activities

LoginActivity.java, RegisterActivity.java, ForgotPasswordActivity.java
Dashboard.java – main dashboard with service cards, offers slider
BannerDetailActivity.java, PosterDetailActivity.java, FlyerDetailActivity.java
BusinessCardActivity.java, StickerDetailActivity.java, MerchandiseOrderActivity.java
HistoryActivity.java, NotificationActivity.java, PublicForumActivity.java, ProfileActivity.java
SplashActivity.java, ViewBookActivity.java (alias for orders)

Adapters

HistoryAdapter.java – orders list
CommentAdapter.java – forum comments
NotificationAdapter.java – notifications list
OfferAdapter.java – ViewPager2 offers slider

Firebase

FirebaseHelper.java – wrapper for Firebase Auth, Database, Storage; includes placeOrder, addUserWithId, sendPasswordResetEmail, etc.

Models

Order.java, User.java, Notification.java, Comment.java, Offer.java
