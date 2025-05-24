# OneStopForWeb

![image](https://github.com/user-attachments/assets/56358770-e2b2-4bde-92b5-fe153970363c)

**OneStopForWeb** is a student‐portal web app built with Express.js, EJS templates, and MongoDB. It bundles common campus utilities in one place:

- **User Auth**: register/login (roll-number + password)  
- **Shop Listings**: buy/sell items with images and contact info  
- **Lost & Found**: report lost or found items, browse current listings  
- **Course Notes**: upload & download notes per course  
- **Timetable**: view daily schedule by department/semester  
- **Menu**: breakfast/lunch/dinner menu by weekday  
- **CPI Calculator**: compute cumulative performance index on the fly  

All views are rendered server-side with EJS and styled via a shared `styles.css`.

---

## 🛠 Tech Stack & Dependencies

- **Runtime**: Node.js v14+  
- **Server**: [Express 4.x](https://expressjs.com/)  
- **Templating**: EJS  
- **Session**: `express-session`  
- **Database**: MongoDB (native `mongodb` driver)  
- **File Uploads**: `multer`  
- **Static Assets**: CSS under `public/`, uploads under `uploads/`  

---

## 🔑 Prerequisites

- **Node.js** and **npm** installed  
- **MongoDB** server (local or Atlas)  
- Environment variables in a `.env` file or your shell:
  ```bash
  MONGODB_URI=<your MongoDB connection string>
  SESSION_SECRET=<a random session secret>
  PORT=3000         # optional, defaults to 3000
  ```

---

## 🚀 Installation & Running Locally

1. **Clone & ignore dependencies**  
   ```bash
   git clone https://github.com/avneesh10115/OneStopForWeb.git
   cd OneStopForWeb
   echo "node_modules/" > .gitignore
   ```
2. **Install dependencies**  
   ```bash
   npm install
   ```
3. **Configure environment**  
   Create a `.env` (or export):
   ```bash
   MONGODB_URI="mongodb://localhost:27017/oneStopWeb"
   SESSION_SECRET="supersecret123"
   PORT=3000
   ```
4. **Start the server**  
   ```bash
   npm start
   ```
5. **Open in browser**  
   Visit <http://localhost:3000>

---

## 📁 Project Structure

```
OneStopForWeb/
├── server.js
├── package.json
├── .gitignore
├── public/               # static assets (styles.css, client JS)
├── uploads/              # multer file uploads (notes, images)
└── views/                # EJS templates
    ├── inc/
    │   └── header.ejs    # common header/navigation
    ├── index.ejs
    ├── register.ejs
    ├── login.ejs
    ├── shop.ejs
    ├── shopAdd.ejs
    ├── lost.ejs
    ├── lostAdd.ejs
    ├── found.ejs
    ├── foundAdd.ejs
    ├── lostAndFound.ejs
    ├── notes.ejs
    ├── notesAdd.ejs
    ├── timetable.ejs
    ├── menu.ejs
    └── cpicalc.ejs
```

---

## 🔗 API Routes & Usage

| Method | Path                   | Description                             |
|--------|------------------------|-----------------------------------------|
| GET    | `/`                    | Home slideshow                          |
| GET    | `/register`            | Show registration form                  |
| POST   | `/register`            | Process new user registration           |
| GET    | `/login`               | Show login form                         |
| POST   | `/login`               | Authenticate user                       |
| GET    | `/logout`              | Logout & destroy session                |
| GET    | `/shop`                | List shop items                         |
| GET    | `/shop/add`            | Show add-item form                      |
| POST   | `/shop/add`            | Upload item + save to MongoDB           |
| GET    | `/shop/remove/:id`     | Delete your listing                     |
| GET    | `/lost`                | List lost items                         |
| GET    | `/lost/add`            | Show add-lost-item form                 |
| POST   | `/lost/add`            | Upload lost item                        |
| GET    | `/lost/remove/:id`     | Remove your lost listing                |
| GET    | `/found`               | List found items                        |
| GET    | `/found/add`           | Show add-found-item form                |
| POST   | `/found/add`           | Upload found item                       |
| GET    | `/found/remove/:id`    | Remove your found listing               |
| GET    | `/lost-and-found`      | Combined lost & found view              |
| GET    | `/notes`               | List & download notes                   |
| GET    | `/notes/add`           | Show add-notes form                     |
| POST   | `/notes/add`           | Upload note file                        |
| GET    | `/notes/remove/:id`    | Delete your note                        |
| GET    | `/timetable`           | View timetable (e.g. `?day=Monday`)     |
| GET    | `/menu`                | View menu (e.g. `?day=Wednesday`)       |

## Hosting

This website is hosted at http://51.79.156.194:3000/
(Timetable is only available for specific departments)

## 📄 License

This project is licensed under the MIT License.
