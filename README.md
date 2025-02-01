# URL Shortener with React & Supabase

A simple and efficient URL Shortener built using **React** for the frontend and **Supabase** as the backend. This project allows users to shorten URLs, track click analytics, and manage their links effectively.

## 🚀 Features

- 🔗 **Shorten Long URLs**: Convert long URLs into short, shareable links.
- 📊 **Click Analytics**: Track the number of times a shortened link is clicked.
- 🧑‍💻 **User Authentication**: Secure login/signup using Supabase authentication.
- 📁 **Link Management**: Users can view, edit, or delete their shortened links.
- 🌐 **Custom Aliases**: Option to create custom short URLs instead of random ones.
- 📅 **Expiration & Deletion**: Set expiration dates for links.
- 📱 **Responsive Design**: Works smoothly on all devices.

## 🛠 Tech Stack

- **Frontend**: React, Tailwind CSS
- **Backend**: Supabase (PostgreSQL, Auth, Realtime DB)
- **Analytics**: Supabase functions & database triggers

## 🏗 Installation & Setup

1. **Clone the repository:**
   ```sh
   git clone https://github.com/yourusername/url-shortener.git
   cd url-shortener
   ```
2. **Install dependencies:**
   ```sh
   npm install
   ```
3. **Set up environment variables:**
   Create a `.env` file and add the following:
   ```sh
   REACT_APP_SUPABASE_URL=your_supabase_url
   REACT_APP_SUPABASE_ANON_KEY=your_anon_key
   ```
4. **Start the development server:**
   ```sh
   npm start
   ```

## 📊 Supabase Database Structure

### `urls` Table

Stores shortened URLs and related metadata.

- `id` (UUID, Primary Key)
- `original_url` (TEXT, Not Null)
- `short_code` (TEXT, Unique, Not Null)
- `user_id` (UUID, Foreign Key to auth.users)
- `created_at` (TIMESTAMP, Default: now())
- `expires_at` (TIMESTAMP, Nullable)

### `clicks` Table

Tracks clicks on shortened URLs.

- `id` (UUID, Primary Key)
- `url_id` (UUID, Foreign Key to urls.id)
- `clicked_at` (TIMESTAMP, Default: now())
- `ip_address` (TEXT, Nullable)
- `user_agent` (TEXT, Nullable)
- `geo_location` (JSONB, Nullable)

## 📊 How Click Analytics Works

- Each time a shortened URL is accessed, a Supabase function updates the click count.
- The dashboard displays analytics including **total clicks**, **geolocation**, and **timestamp**.

## 🔧 Future Enhancements

- 🏷️ **QR Code Generation** for each shortened link.
- 🔐 **Role-Based Access Control** for enterprise users.
- 📈 **Advanced Analytics** with user engagement metrics.
- 🌍 **Custom Domain Support** for branded links.

## 📜 License

This project is licensed under the [MIT License](LICENSE).

## 🤝 Contributing

Contributions are welcome! Feel free to submit issues or pull requests.

## 🌟 Acknowledgments

- [React](https://react.dev/)
- [Supabase](https://supabase.io/)
- [Tailwind CSS](https://tailwindcss.com/)

---

🚀 **Start shortening URLs and tracking clicks now!**
