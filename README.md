# 🌮 TACOS BACOS

A fun and interactive web application built with **Node.js**, **Express**, and **EJS** that dynamically displays delicious taco recipes by parsing structured JSON data.

---

## 📖 Overview

**Tacos Bacos** lets users explore different taco recipes (Chicken, Beef, and Fish) at the click of a button. When a user selects a taco, the server processes the choice, parses recipe data from a JSON dataset, and renders an interactive view showing:
- 🥩 **Protein** type and preparation method
- 🌶️ **Salsa** type and spiciness level
- 🧀 **Toppings** with measured ingredient quantities

---

## ✨ Features

- **Dynamic Templating with EJS**: Renders recipe cards conditionally and loops through topping arrays dynamically.
- **RESTful Express Routing**: Clean handling of `GET /` and `POST /recipe` endpoints with redirect-after-post flow.
- **JSON Data Parsing**: Demonstrates server-side JSON handling and array filtering (`Array.prototype.find`).
- **Clean UI & Responsive Design**: Custom CSS styling with circular emoji button controls and smooth hover effects.

---

## 🛠️ Tech Stack

- **Runtime**: [Node.js](https://nodejs.org/)
- **Framework**: [Express.js](https://expressjs.com/)
- **Templating Engine**: [EJS](https://ejs.co/)
- **Middleware**: [body-parser](https://www.npmjs.com/package/body-parser)
- **Frontend**: HTML5, CSS3

---

## 🚀 Getting Started

### Prerequisites

Make sure you have [Node.js](https://nodejs.org/) (v16 or higher) installed on your machine.

### Installation

1. **Clone the repository:**
   ```bash
   git clone https://github.com/Sharanzwing/TACOS-BACOS.git
   cd TACOS-BACOS
   ```

2. **Install dependencies:**
   ```bash
   npm install
   ```

3. **Start the application:**
   ```bash
   node index.js
   ```

4. **View in browser:**
   Open your browser and navigate to:
   ```
   http://localhost:3000
   ```

---

## 📁 Project Structure

```text
TACOS-BACOS/
├── public/
│   └── styles/
│       └── main.css        # Custom styles and SVG background pattern
├── views/
│   ├── index.ejs           # Main EJS view template
│   └── solution.ejs        # Reference solution template
├── .gitignore              # Files and directories ignored by Git
├── index.js                # Express server entry point & routing
├── package.json            # Project dependencies and metadata
├── recipe.json             # Taco recipe data in JSON format
├── solution.js             # Reference solution server file
└── README.md               # Project documentation
```

---

## ⚙️ How It Works

1. **User Request**: The user visits `http://localhost:3000` and sees an empty recipe prompt.
2. **Form Submission**: Clicking on one of the emoji buttons sends a `POST` request to `/recipe` containing the user's choice (`chicken`, `beef`, or `fish`).
3. **Data Lookup**: The server parses the recipe JSON array and matches the selected taco:
   ```javascript
   const recipes = JSON.parse(recipeJSON);
   recipe = recipes.find((item) =>
     item.name.toLowerCase().startsWith(req.body.choice)
   );
   ```
4. **Render**: The user is redirected back to `/`, where EJS dynamically generates the HTML with the matching recipe's name, protein, salsa, and list of toppings.

---

## 📄 License

This project is open source and available under the [ISC License](LICENSE).