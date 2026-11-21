<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Unblocked Hub</title>

<style>
* {
    box-sizing: border-box;
}

body {
    margin: 0;
    background: #090914;
    color: white;
    font-family: Arial, sans-serif;
}

header {
    padding: 25px;
    text-align: center;
    background: #111126;
    border-bottom: 2px solid #a855f7;
    box-shadow: 0 0 20px #8b5cf6;
}

header h1 {
    margin: 0;
    font-size: 35px;
    color: #35e7ff;
    text-shadow: 0 0 15px #35e7ff;
}

header p {
    color: #aaa;
}

.container {
    max-width: 1100px;
    margin: auto;
    padding: 25px;
}

.search {
    width: 100%;
    padding: 16px;
    border-radius: 12px;
    border: 1px solid #35e7ff;
    background: #17172b;
    color: white;
    font-size: 16px;
    outline: none;
    margin-bottom: 20px;
}

.search:focus {
    box-shadow: 0 0 15px #35e7ff;
}

.categories {
    display: flex;
    flex-wrap: wrap;
    gap: 10px;
    margin-bottom: 25px;
}

.categories button {
    padding: 11px 17px;
    border: 1px solid #a855f7;
    background: #17172b;
    color: white;
    border-radius: 20px;
    cursor: pointer;
}

.categories button:hover,
.categories button.active {
    background: #a855f7;
    box-shadow: 0 0 12px #a855f7;
}

.section-title {
    margin-bottom: 18px;
    color: #35e7ff;
}

.games {
    display: grid;
    grid-template-columns: repeat(
        auto-fit,
        minmax(220px, 1fr)
    );
    gap: 18px;
}

.card {
    background: #15152b;
    border: 1px solid #33335a;
    border-radius: 15px;
    padding: 20px;
    transition: 0.2s;
}

.card:hover {
    transform: translateY(-5px);
    border-color: #35e7ff;
    box-shadow: 0 0 18px #35e7ff55;
}

.card h3 {
    color: #35e7ff;
}

.card p {
    color: #aaa;
    min-height: 42px;
    font-size: 14px;
    line-height: 1.5;
}

.card-buttons {
    display: flex;
    gap: 8px;
    align-items: center;
}

.visit {
    flex: 1;
    text-decoration: none;
    text-align: center;
    background: linear-gradient(90deg, #35e7ff, #a855f7);
    color: #090914;
    padding: 11px;
    border-radius: 8px;
    font-weight: bold;
}

.favourite {
    background: #292943;
    color: #ff55c8;
    border: 1px solid #555;
    padding: 9px 12px;
    border-radius: 8px;
    cursor: pointer;
    font-size: 18px;
}

.favourite.saved {
    background: #542044;
}

.empty {
    display: none;
    text-align: center;
    color: #aaa;
    padding: 30px;
}

footer {
    text-align: center;
    color: #777;
    padding: 30px;
    font-size: 13px;
}
</style>
</head>

<body>

<header>
    <h1>✦ UNBLOCKED HUB</h1>
    <p>Your gateway to gaming.</p>
</header>

<div class="container">

    <input
        type="text"
        id="search"
        class="search"
        placeholder="🔎 Search gaming websites..."
    >

    <div class="categories" id="categories">
        <button class="active" data-category="All">All</button>
        <button data-category="Arcade">Arcade</button>
        <button data-category="Puzzle">Puzzle</button>
        <button data-category="Racing">Racing</button>
        <button data-category="Casual">Casual</button>
        <button data-category="Multiplayer">Multiplayer</button>
        <button data-category="Favourites">❤️ Favourites</button>
    </div>

    <h2 class="section-title" id="sectionTitle">
        🎮 Gaming Websites
    </h2>

    <div class="games" id="games"></div>

    <div class="empty" id="empty">
        No websites found!
    </div>

</div>

<footer>
    UNBLOCKED HUB V1.0<br>
    Independent gaming website directory.<br>
    Website access depends on network settings and each site's availability.
</footer>

<script>

const websites = [
    {
        name: "Totally Science",
        icon: "🧪",
        description: "Explore a collection of browser games.",
        url: "https://totallyscience.app/games/",
        categories: ["Arcade", "Puzzle", "Racing"]
    },
    {
        name: "Completely Science",
        icon: "⚗️",
        description: "Discover games across different genres.",
        url: "https://completely-science.com/",
        categories: ["Arcade", "Puzzle", "Casual"]
    },
    {
        name: "FreezeNova Games",
        icon: "❄️",
        description: "A collection of free online games.",
        url: "https://freezenova.com/",
        categories: ["Arcade", "Racing", "Casual"]
    },
    {
        name: "FreezeNova Games Cloud",
        icon: "☁️",
        description: "Explore a cloud-hosted game portal.",
        url: "https://cloud.totallyscience.co/index.html",
        categories: ["Arcade", "Puzzle", "Casual"]
    },
    {
        name: "Coolmath Games",
        icon: "🧠",
        description: "Logic, strategy and skill games.",
        url: "https://www.coolmathgames.com/",
        categories: ["Puzzle", "Casual"]
    },
    {
        name: "Definitely Science",
        icon: "🔬",
        description: "Browse a variety of online games.",
        url: "https://definitelyscience.com/",
        categories: ["Arcade", "Multiplayer"]
    },
    {
        name: "CrazyGames",
        icon: "🎮",
        description: "A huge library of browser games.",
        url: "https://www.crazygames.com/",
        categories: ["Arcade", "Racing", "Puzzle", "Multiplayer"]
    },
    {
        name: "Poki",
        icon: "🕹️",
        description: "Play free online games.",
        url: "https://poki.com/",
        categories: ["Arcade", "Casual", "Multiplayer"]
    },
    {
        name: "itch.io",
        icon: "🎨",
        description: "Discover independent HTML5 games.",
        url: "https://itch.io/games/html5",
        categories: ["Arcade", "Puzzle", "Casual"]
    },
    {
        name: "GamePix",
        icon: "👾",
        description: "Explore a wide browser game catalogue.",
        url: "https://www.gamepix.com/",
        categories: ["Arcade", "Racing", "Casual"]
    }
];

let currentCategory = "All";
let favourites = new Set();

try {
    favourites = new Set(
        JSON.parse(
            localStorage.getItem("hubFavourites") || "[]"
        )
    );
} catch (error) {
    favourites = new Set();
}

const games = document.getElementById("games");
const search = document.getElementById("search");
const empty = document.getElementById("empty");

function render() {

    const query = search.value.toLowerCase();

    const filtered = websites.filter(site => {

        const matchesSearch =
            site.name.toLowerCase().includes(query) ||
            site.description.toLowerCase().includes(query) ||
            site.categories.join(" ").toLowerCase().includes(query);

        const matchesCategory =
            currentCategory === "All" ||
            (
                currentCategory === "Favourites"
                    ? favourites.has(site.name)
                    : site.categories.includes(currentCategory)
            );

        return matchesSearch && matchesCategory;
    });

    games.innerHTML = "";

    filtered.forEach(site => {

        const card = document.createElement("div");
        card.className = "card";

        const heading = document.createElement("h3");
        heading.textContent = site.icon + " " + site.name;

        const description = document.createElement("p");
        description.textContent = site.description;

        const buttons = document.createElement("div");
        buttons.className = "card-buttons";

        const visit = document.createElement("a");
        visit.className = "visit";
        visit.href = site.url;
        visit.target = "_blank";
        visit.rel = "noopener noreferrer";
        visit.textContent = "Visit Website ↗";

        const favourite = document.createElement("button");
        favourite.className = "favourite";
        favourite.textContent =
            favourites.has(site.name) ? "♥" : "♡";

        if (favourites.has(site.name)) {
            favourite.classList.add("saved");
        }

        favourite.setAttribute(
            "aria-label",
            "Toggle favourite for " + site.name
        );

        favourite.addEventListener("click", () => {

            if (favourites.has(site.name)) {
                favourites.delete(site.name);
            } else {
                favourites.add(site.name);
            }

            try {
                localStorage.setItem(
                    "hubFavourites",
                    JSON.stringify([...favourites])
                );
            } catch (error) {}

            render();
        });

        buttons.appendChild(visit);
        buttons.appendChild(favourite);

        card.appendChild(heading);
        card.appendChild(description);
        card.appendChild(buttons);

        games.appendChild(card);
    });

    empty.style.display =
        filtered.length === 0 ? "block" : "none";
}

search.addEventListener("input", render);

document.getElementById("categories")
.addEventListener("click", event => {

    if (event.target.tagName !== "BUTTON") return;

    currentCategory = event.target.dataset.category;

    document.querySelectorAll(".categories button")
    .forEach(button => {
        button.classList.toggle(
            "active",
            button === event.target
        );
    });

    document.getElementById("sectionTitle").textContent =
        currentCategory === "Favourites"
            ? "❤️ Your Favourites"
            : currentCategory === "All"
                ? "🎮 Gaming Websites"
                : "🎮 " + currentCategory + " Websites";

    render();
});

render();

</script>

</body>
</html>
