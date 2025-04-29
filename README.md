# 🎧 Music Store Database Schema

This repository contains the Entity-Relationship Diagram (ERD) for a **Music Store Management System**. It models the relationships between customers, songs, playlists, artists, albums, payments, subscriptions, and more.

## 📊 ER Diagram

![Music Store ER Diagram](./ERR%20daigram.png)

---

## 🗂️ Entity Descriptions

### **1. Customer**
Represents users of the platform.
- `customer_id` (PK)
- `name`
- `email`
- `registration_date`

### **2. Subscription**
Tracks subscription plans of customers.
- `subscription_id` (PK)
- `customer_id` (FK)
- `plan`
- `start_date`
- `end_date`
- `is_active` (boolean)

### **3. Purchase**
Records purchases made by customers.
- `purchase_id` (PK)
- `customer_id` (FK)
- `purchase_date`
- `total_amount`

### **4. Payment**
Logs payment details for each purchase.
- `payment_id` (PK)
- `purchase_id` (FK)
- `method` (e.g., card, PayPal)
- `status` (e.g., completed, pending)
- `payment_date`

### **5. PurchasedDetail**
Links songs to purchases (many-to-many relationship).
- `purchase_id` (FK)
- `song_id` (FK)

### **6. Song**
Contains individual song data.
- `song_id` (PK)
- `title`
- `duration`
- `price`
- `album_id` (FK)
- `genre_id` (FK)

### **7. Album**
Albums grouping multiple songs.
- `album_id` (PK)
- `title`
- `release_year`
- `artist_id` (FK)

### **8. Artist**
Musicians who produce albums and songs.
- `artist_id` (PK)
- `name`

### **9. Genre**
Categorizes songs by genre.
- `genre_id` (PK)
- `name`

### **10. Review**
Customer reviews for songs.
- `review_id` (PK)
- `customer_id` (FK)
- `song_id` (FK)
- `rating` (numeric)
- `comment`
- `review_date`

### **11. Playlist**
Customer-created song collections.
- `playlist_id` (PK)
- `name`
- `customer_id` (FK)
- `created_at`

### **12. PlaylistSong**
Associates songs to playlists (many-to-many).
- `playlist_id` (FK)
- `song_id` (FK)

---

## 🔁 Relationships

- **One-to-Many**: A customer can have many subscriptions, purchases, playlists, and reviews.
- **Many-to-Many**: 
  - Songs can belong to multiple playlists and purchases.
  - Playlists can contain multiple songs.
- **One-to-One**: Each payment is tied to one purchase.
- **Belongs-To**: 
  - Songs belong to albums and genres.
  - Albums are created by artists.

---

## 🛠️ Use Cases

- Building a backend for a music streaming or purchase platform.
- Designing relational queries for data analysis.
- Learning relational database design with complex relationships.

---

## 📁 Files

- `ERR daigram.png` – Visual representation of the ER model.
- (Optional) SQL schema or seed data files can be added later.

---

## 🧠 Contributing

Feel free to contribute enhancements, improvements, or SQL implementations based on this schema.


