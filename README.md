<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>The Ultimate Quilt Resource Hub</title>
  <script src="https://cdn.tailwindcss.com"></script>
  <style>
    body {
      background: #fafaf9;
      font-family: "Inter", sans-serif;
    }
    header {
      text-align: center;
      margin-bottom: 2.5rem;
    }
    header h1 {
      font-weight: 900;
      font-size: 3rem;
      color: #716A56;
      letter-spacing: -0.02em;
      margin: 0;
    }
    header p {
      color: #716A56;
      font-size: 1rem;
      font-weight: 500;
      margin-top: 0.75rem;
      margin-bottom: 0;
    }
    .category-checkboxes {
      display: flex;
      flex-wrap: wrap;
      gap: 0.75rem;
      justify-content: center;
      margin-bottom: 2rem;
    }
    .category-checkboxes input[type="checkbox"] {
      display: none;
    }
    .category-checkboxes label {
      cursor: pointer;
      padding: 0.5rem 1rem;
      border-radius: 9999px;
      background: #e8e3d7;
      color: #716A56;
      font-weight: 600;
      border: 2px solid transparent;
      transition: all 0.3s ease;
      user-select: none;
      box-shadow: 0 1px 3px rgb(0 0 0 / 0.1);
      font-size: 0.85rem;
    }
    .category-checkboxes input[type="checkbox"]:checked + label {
      background: #716A56;
      color: white;
      border-color: #5b5347;
      box-shadow: 0 10px 15px -3px rgb(113 106 86 / 0.5);
      transform: scale(1.05);
    }
    .category-checkboxes label:hover {
      border-color: #5b5347;
    }
    #directory {
      max-width: 900px;
      margin: 0 auto;
      display: flex;
      flex-direction: column;
      gap: 1.5rem;
    }
    .card {
      background: white;
      border-radius: 1rem;
      padding: 1.5rem 1.5rem;
      box-shadow: 0 8px 32px rgb(113 106 86 / 0.15);
      transition: box-shadow 0.3s ease, transform 0.2s ease;
      border: 1px solid #716A56;
      width: 100%;
      display: flex;
      flex-direction: column;
      gap: 1rem;
      align-items: center;
    }
    @media (min-width: 640px) {
      .card {
        flex-direction: row;
        gap: 1.5rem;
        align-items: flex-start;
        padding: 2rem;
      }
    }
    .photo {
      flex-shrink: 0;
      width: 96px;
      height: 96px;
      border-radius: 0.75rem;
      object-fit: cover;
      background: #ede9de;
    }
    @media (min-width: 640px) {
      .photo {
        width: 120px;
        height: 120px;
      }
    }
    .card-content {
      flex-grow: 1;
      width: 100%;
    }
    .card-content h2 {
      font-size: 1.5rem;
      font-weight: 800;
      color: #716A56;
      margin-bottom: 0.5rem;
      user-select: text;
    }
    @media (min-width: 640px) {
      .card-content h2 {
        font-size: 1.75rem;
      }
    }
    .category-badge {
      display: inline-block;
      padding: 0.2rem 0.8rem;
      border-radius: 9999px;
      font-weight: 600;
      margin-bottom: 0.75rem;
      user-select: none;
      width: fit-content;
      color: white;
      font-size: 0.8rem;
      margin-right: 0.4rem;
      margin-top: 0.3rem;
    }
    /* Category badge colors */
    .category-badge.bg-red-400 { background-color: #a05959; }
    .category-badge.bg-green-500 { background-color: #6d6a52; }
    .category-badge.bg-blue-500 { background-color: #708090; }
    .category-badge.bg-yellow-400 { background-color: #b0a675; color: #3a331a; }
    .category-badge.bg-indigo-500 { background-color: #665f84; }
    .category-badge.bg-pink-500 { background-color: #9d7b7f; }
    .category-badge.bg-purple-500 { background-color: #7a6b8d; }
    .category-badge.bg-orange-400 { background-color: #ad865a; }
    .category-badge.bg-teal-500 { background-color: #5f7d7b; }
    .category-badge.bg-gray-400 { background-color: #9e998b; }

    .info-label {
      font-weight: 700;
      color: #716A56;
      margin-top: 1rem;
      user-select: none;
      font-size: 0.9rem;
    }
    .info-text {
      color: #5a574a;
      font-weight: 500;
      margin-top: 0.25rem;
      white-space: pre-line;
      user-select: text;
      font-size: 0.9rem;
      overflow-wrap: break-word;
    }
    a.info-link {
      color: #716A56;
      font-weight: 700;
      text-decoration: none;
      transition: color 0.3s ease;
      word-break: break-word;
    }
    a.info-link:hover {
      color: #5b5347;
      text-decoration: underline;
    }
    .submit-container {
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
      margin-bottom: 1rem;
    }
    .submit-button {
      background-color: #716A56;
      color: white;
      font-weight: 700;
      font-size: 1.1rem;
      padding: 0.75rem 1.8rem;
      border-radius: 9999px;
      box-shadow: 0 10px 15px -3px rgb(113 106 86 / 0.5);
      border: none;
      cursor: pointer;
      display: inline-flex;
      align-items: center;
      transition: background-color 0.3s ease, transform 0.15s ease;
    }
    .submit-button svg {
      margin-right: 0.6rem;
      stroke: currentColor;
      width: 20px;
      height: 20px;
    }
    .submit-button:hover {
      background-color: #5b5347;
      transform: translateY(-2px);
    }
    .submit-button:active {
      transform: scale(0.95);
    }
    .submit-button:focus-visible {
      outline: 3px solid #8c8473;
      outline-offset: 3px;
    }
    .free-service-text {
      font-size: 1rem;
      color: #716A56;
      font-weight: 600;
      margin-top: 0.5rem;
      user-select: none;
    }
    #search-container {
      display: flex;
      justify-content: center;
      margin-bottom: 2.5rem;
    }
    #search-bar {
      width: 90%;
      max-width: 600px;
      padding: 0.5rem 1rem;
      font-size: 1rem;
      color: #5a574a;
      border: 2px solid #716A56;
      border-radius: 9999px;
      box-shadow: 0 1px 3px rgb(0 0 0 / 0.1);
      transition: box-shadow 0.3s ease, border-color 0.3s ease, outline 0.3s ease;
    }
    #search-bar:focus {
      outline: none;
      border-color: #5b5347;
      box-shadow: 0 0 8px #716A56;
    }
    .vcard-button {
      background-color: white;
      color: #716A56;
      padding: 0.4rem 1rem;
      border-radius: 9999px;
      font-weight: 600;
      cursor: pointer;
      border: 2px solid #716A56;
      transition: background-color 0.3s ease, color 0.3s ease;
      margin-top: 1rem;
      user-select: none;
      font-size: 0.875rem;
      display: inline-flex;
      align-items: center;
      justify-content: center;
    }
    .vcard-button:hover {
      background-color: #716A56;
      color: white;
    }
    .vcard-button:active {
      transform: scale(0.95);
    }
  </style>
</head>
<body>

  <!-- Larger, centered logo, no star -->
  <div style="text-align:center; margin-top:2rem; margin-bottom:2rem;">
    <svg xmlns="http://www.w3.org/2000/svg" class="inline-block h-48 w-48" viewBox="0 0 64 64" fill="none" stroke="#716A56" stroke-width="2" stroke-linejoin="round" stroke-linecap="round" aria-label="Quilt patchwork logo">
      <rect x="2" y="2" width="60" height="60" fill="#f5f2e7" stroke="#716A56" stroke-width="3"/>
      <line x1="22" y1="2" x2="22" y2="62" stroke="#716A56" stroke-dasharray="4 2"/>
      <line x1="42" y1="2" x2="42" y2="62" stroke="#716A56" stroke-dasharray="4 2"/>
      <line x1="2" y1="22" x2="62" y2="22" stroke="#716A56" stroke-dasharray="4 2"/>
      <line x1="2" y1="42" x2="62" y2="42" stroke="#716A56" stroke-dasharray="4 2"/>
      <rect x="2" y="2" width="20" height="20" fill="#c7b29f"/>
      <rect x="22" y="2" width="20" height="20" fill="#b3a27b"/>
      <rect x="42" y="2" width="20" height="20" fill="#a98c6c"/>
      <rect x="2" y="22" width="20" height="20" fill="#d8c9b9"/>
      <rect x="22" y="22" width="20" height="20" fill="#716a56"/>
      <rect x="42" y="22" width="20" height="20" fill="#bba06f"/>
      <rect x="2" y="42" width="20" height="20" fill="#dbd3bf"/>
      <rect x="22" y="42" width="20" height="20" fill="#a49267"/>
      <rect x="42" y="42" width="20" height="20" fill="#9c8f78"/>
    </svg>
  </div>

  <header>
    <h1>The Ultimate Quilt Resource Hub</h1>
    <p>A vibrant resource hub connecting you to quilt guilds, local quilt stores, exciting quilt shows, professional organizations, expert longarm services, and inspiring fiber art galleries.</p>
  </header>

  <div class="submit-container">
    <button id="submit-button" class="submit-button" aria-label="Submit new resource">
      <svg fill="none" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" viewBox="0 0 24 24" stroke="currentColor" aria-hidden="true">
        <path d="M12 5v14m7-7H5"></path>
      </svg>
      Submit a Resource
    </button>
    <span class="free-service-text">100% always free</span>
  </div>

  <div id="search-container">
    <input id="search-bar" type="search" placeholder="Search by name, location, or keyword..." aria-label="Search resources" />
  </div>

  <section class="category-checkboxes" id="category-filter" role="group" aria-label="Filter categories"></section>

  <main id="directory" aria-live="polite">
    <p class="text-center text-gray-500 text-xl py-20">Loading directory...</p>
  </main>

  <script>
    // The JavaScript code for loading data, handling filters, and rendering cards remains unchanged from your previous version
    const API_URL = "https://script.google.com/macros/s/AKfycbwbTnAGAkjxSSLmaAPcF4RDLDbySQp2zHxwvbJUubeDryirbpoGfaBmpBZ5mbe82ugD/exec";

    const NAME_KEY = "Resource/Business Name:";
    const CATEGORY_KEY = "Resource Type/Category:";
    const LOCATION_KEY = "Full Location (City, State/Province, Country):";
    const EMAIL_KEY = "Contact Email Address:";
    const WEBSITE_KEY = "Website URL (or Etsy/Blog):";
    const INSTAGRAM_KEY = "Instagram Handle:";
    const FACEBOOK_KEY = "Facebook Page URL:";
    const PHOTO_KEY = "Logo or Profile Photo:";
    const BIO_KEY = "Brief Description / Bio:";
    const TIMESTAMP_KEY = "Timestamp";

    const CATEGORY_COLORS = {
      "Quilt Guilds": "bg-red-400 text-white",
      "Local Quilt Store": "bg-green-500 text-white",
      "Online Quilt Store": "bg-blue-500 text-white",
      "Quilt Shows": "bg-yellow-400 text-black",
      "Professional Organisations": "bg-indigo-500 text-white",
      "Quilt Pattern Designers": "bg-pink-500 text-white",
      "Quilt Teachers & Educators": "bg-purple-500 text-white",
      "Longarm Services": "bg-orange-400 text-white",
      "Fiber Art Galleries": "bg-teal-500 text-white",
      "All Resources (A-Z Name)": "bg-gray-400 text-white",
    };

    let allEntries = [];
    let selectedCategories = [];

    const RESOURCE_CATEGORIES = [
      "All Resources (A-Z Name)",
      "Quilt Guilds",
      "Local Quilt Store",
      "Online Quilt Store",
      "Quilt Shows",
      "Professional Organisations",
      "Quilt Pattern Designers",
      "Quilt Teachers & Educators",
      "Longarm Services",
      "Fiber Art Galleries",
    ];

    function normalizeWebsiteUrl(url) {
      if (!url) return "";
      url = url.trim();
      url = url.replace(/^(https?:\/\/)?(www\.)?/i, "");
      return "http://www." + url;
    }

    async function fetchData() {
      try {
        const res = await fetch(API_URL);
        if (!res.ok) throw new Error("Network error");
        const data = await res.json();
        allEntries = data.filter((entry) => entry[NAME_KEY]);
      } catch (err) {
        console.error(err);
        allEntries = [];
      }
    }

    function createCategoryCheckbox(category) {
      const id = `cat-${category.toLowerCase().replace(/[^a-z0-9]/g, "-")}`;
      const checkedAttr = category === "All Resources (A-Z Name)" ? "checked" : "";
      return `
        <input type="checkbox" id="${id}" name="category" value="${category}" ${checkedAttr} aria-checked="${checkedAttr ? "true" : "false"}"/>
        <label for="${id}" tabindex="0">${category}</label>
      `;
    }

    function renderCategoryFilters() {
      const container = document.getElementById("category-filter");
      container.innerHTML = RESOURCE_CATEGORIES.map(createCategoryCheckbox).join("");
      container.querySelectorAll("input[name='category']").forEach((cb) => {
        cb.addEventListener("change", onCategoryChange);
      });
    }

    function onCategoryChange(e) {
      const val = e.target.value;

      if (val === "All Resources (A-Z Name)") {
        if (e.target.checked) {
          selectedCategories = ["All Resources (A-Z Name)"];
          [...document.querySelectorAll("input[name='category']")].forEach((input) => {
            if (input.value !== val) {
              input.checked = false;
              input.setAttribute("aria-checked", "false");
            }
          });
        } else {
          e.target.checked = true;
          return;
        }
      } else {
        if (e.target.checked) {
          selectedCategories = selectedCategories.filter((cat) => cat !== "All Resources (A-Z Name)");
          selectedCategories.push(val);
        } else {
          selectedCategories = selectedCategories.filter((cat) => cat !== val);
          if (selectedCategories.length === 0) {
            const allCb = document.querySelector("input[value='All Resources (A-Z Name)']");
            allCb.checked = true;
            allCb.setAttribute("aria-checked", "true");
            selectedCategories = ["All Resources (A-Z Name)"];
          }
        }
      }
      e.target.setAttribute("aria-checked", e.target.checked.toString());
      const currentQuery = document.getElementById("search-bar").value || "";
      applySortAndFilter(currentQuery);
    }

    function escapeHTML(str) {
      if (!str) return "";
      return String(str).replace(/[&<>"']/g, (c) => {
        return { "&": "&amp;", "<": "&lt;", ">": "&gt;", '"': "&quot;", "'": "''" }[c];
      });
    }

    function generateVCard(entry) {
      const name = entry[NAME_KEY] || "";
      const email = entry[EMAIL_KEY] || "";
      const location = entry[LOCATION_KEY] || "";
      const url = entry[WEBSITE_KEY] || "";
      const instagram = entry[INSTAGRAM_KEY] || "";
      const bio = (entry[BIO_KEY] || "").replace(/\r?\n|\r/g, "\\n");

      return `BEGIN:VCARD
VERSION:3.0
FN:${name}
EMAIL;TYPE=INTERNET:${email}
ADR;TYPE=WORK:;;${location.replace(/,/g, ";")}
URL:${url}
NOTE:${bio}${instagram ? "\\nInstagram: @" + instagram : ""}
END:VCARD`;
    }

    function createCard(entry) {
      const photoUrl = entry[PHOTO_KEY] && /\.(jpe?g|png|gif|webp)$/i.test(entry[PHOTO_KEY]) ? escapeHTML(entry[PHOTO_KEY]) : null;
      const instagramHandle = entry[INSTAGRAM_KEY] ? entry[INSTAGRAM_KEY].replace(/^@/, "") : null;
      const facebookUrl = entry[FACEBOOK_KEY] || null;
      const locationQuery = entry[LOCATION_KEY] ? encodeURIComponent(entry[LOCATION_KEY]) : null;

      let categoryBadges = "";
      if (entry[CATEGORY_KEY]) {
        const splitCats = entry[CATEGORY_KEY].split(/[,\/]/).map(c => c.trim());
        categoryBadges = splitCats.map(cat => {
          const colorClass = CATEGORY_COLORS[cat] || "bg-gray-400 text-white";
          return `<span class="category-badge ${colorClass}">${escapeHTML(cat)}</span>`;
        }).join(" ");
      }

      const normalizedWebsite = normalizeWebsiteUrl(entry[WEBSITE_KEY]);
      const cardId = entry[NAME_KEY].toLowerCase().replace(/\s+/g, "-").replace(/[^a-z0-9\-]/g, "");

      return `
        <article class="card" role="listitem" tabindex="0" aria-label="${escapeHTML(entry[NAME_KEY])}">
          ${photoUrl ? `<img src="${photoUrl}" alt="Logo or photo of ${escapeHTML(entry[NAME_KEY])}" class="photo" loading="lazy">` : ""}
          <div class="card-content">
            <h2>${escapeHTML(entry[NAME_KEY])}</h2>
            <div>${categoryBadges}</div>
            ${entry[LOCATION_KEY] ? `<p class="info-label mt-4">Location</p><p class="info-text location"><a href="https://www.google.com/maps/search/?api=1&query=${locationQuery}" target="_blank" rel="noopener noreferrer" class="info-link">${escapeHTML(entry[LOCATION_KEY])}</a></p>` : ""}
            ${entry[EMAIL_KEY] ? `<p class="info-label mt-4">Email</p><p class="info-text"><a href="mailto:${escapeHTML(entry[EMAIL_KEY])}" class="info-link">${escapeHTML(entry[EMAIL_KEY])}</a></p>` : ""}
            ${instagramHandle ? `<p class="info-label mt-4">Instagram</p><p class="info-text instagram"><a href="https://instagram.com/${instagramHandle}" target="_blank" rel="noopener noreferrer" class="info-link">@${escapeHTML(instagramHandle)}</a></p>` : ""}
            ${facebookUrl ? `<p class="info-label mt-4">Facebook</p><p class="info-text facebook"><a href="${escapeHTML(facebookUrl)}" target="_blank" rel="noopener noreferrer" class="info-link">${escapeHTML(facebookUrl)}</a></p>` : ""}
            ${entry[BIO_KEY] ? `<p class="info-label mt-4">About</p><p class="info-text">${escapeHTML(entry[BIO_KEY])}</p>` : ""}
            ${normalizedWebsite ? `<p class="info-label mt-4">Website</p><p class="info-text website"><a href="${normalizedWebsite}" target="_blank" rel="noopener noreferrer" class="info-link">${normalizedWebsite}</a></p>` : ""}
            ${entry[TIMESTAMP_KEY] ? `<p class="info-label mt-4">Submitted</p><p class="info-text">${escapeHTML(entry[TIMESTAMP_KEY])}</p>` : ""}
            <button id="download-vcard-${cardId}" class="vcard-button" aria-label="Download vCard for ${escapeHTML(entry[NAME_KEY])}">
              Download vCard
            </button>
          </div>
        </article>`;
    }

    function renderDirectory(entries) {
      const container = document.getElementById("directory");
      if (!entries.length) {
        container.innerHTML = `<p class="text-center text-gray-500 text-xl py-20">No directory entries found.</p>`;
        return;
      }
      container.innerHTML = entries.map(createCard).join("");

      entries.forEach(entry => {
        const cardId = entry[NAME_KEY].toLowerCase().replace(/\s+/g, "-").replace(/[^a-z0-9\-]/g, "");
        const btn = document.getElementById(`download-vcard-${cardId}`);
        if (btn) {
          btn.addEventListener("click", () => {
            const vcardText = generateVCard(entry);
            const blob = new Blob([vcardText], { type: "text/vcard" });
            const link = document.createElement("a");
            link.href = URL.createObjectURL(blob);
            link.download = `${entry[NAME_KEY].replace(/[^a-z0-9]/gi, "_")}.vcf`;
            document.body.appendChild(link);
            link.click();
            document.body.removeChild(link);
          });
        }
      });
    }

    async function init() {
      await fetchData();
      renderCategoryFilters();
      selectedCategories = ["All Resources (A-Z Name)"];
      applySortAndFilter("");
    }

    document.addEventListener("DOMContentLoaded", () => {
      init();

      document.getElementById("search-bar").addEventListener("input", e => {
        applySortAndFilter(e.target.value);
      });

      document.getElementById("submit-button").addEventListener("click", () => {
        window.open(
          "https://docs.google.com/forms/d/e/1FAIpQLSeFtU0Bm1k6cI3Vep-4Zeb5BzDgUX8F5qp8-SFdo7P-KWkIGQ/viewform",
          "_blank",
          "noopener"
        );
      });
    });

    function applySortAndFilter(query) {
      const q = query.toLowerCase().trim();

      let results = allEntries.filter(entry => {
        if (!entry || !entry[NAME_KEY]) return false;

        if (q) {
          const haystack = Object.values(entry).join(" ").toLowerCase();
          if (!haystack.includes(q)) return false;
        }

        if (selectedCategories.length && !selectedCategories.includes("All Resources (A-Z Name)")) {
          const entryCats = (entry[CATEGORY_KEY] || "").toLowerCase().split(/[,\/]/).map(c => c.trim());
          const match = selectedCategories.some(cat =>
            entryCats.some(ec => ec.includes(cat.toLowerCase()))
          );
          if (!match) return false;
        }
        return true;
      });

      results.sort((a, b) => (a[NAME_KEY] || "").toLowerCase().localeCompare((b[NAME_KEY] || "").toLowerCase()));

      renderDirectory(results);
    }
  </script>

</body>
</html>
