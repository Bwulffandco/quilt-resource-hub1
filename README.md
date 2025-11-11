<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>🌟 The Ultimate Quilt Resource Hub</title>

    <meta http-equiv="Content-Security-Policy" content="default-src 'self'; 
         script-src 'self' 'unsafe-inline' https://cdn.tailwindcss.com https://maps.googleapis.com; 
         style-src 'self' 'unsafe-inline' https://cdn.tailwindcss.com https://fonts.googleapis.com;
         font-src 'self' https://fonts.gstatic.com;
         connect-src 'self' https://api.sheetbest.com https://maps.googleapis.com; /* Allows connection to Sheet Best */
         img-src 'self' data: https://maps.googleapis.com https://*.googleusercontent.com https://i.imgur.com; 
         frame-ancestors 'self';">
    <script src="https://cdn.tailwindcss.com"></script>
    <link rel="stylesheet" href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700;800&display=swap">
    
    <script>
        tailwind.config = {
            theme: {
                extend: {
                    colors: {
                        'primary': {
                            50: '#f7fee7',
                            100: '#ecfccb',
                            200: '#d9f99d',
                            300: '#c0ff2d', 
                            400: '#a3e635',
                            500: '#84cc16', 
                            600: '#65a30d', 
                            700: '#4d7c0f',
                            800: '#3f6212',
                            900: '#365314',
                            950: '#1a2e05',
                        },
                    }
                }
            }
        }
    </script>
    <style>
        /* Set font and background for the app */
        #directory-app-container {
            font-family: 'Inter', sans-serif;
            background-color: #f8fafc;
            min-height: 100vh;
        }
        .modern-mom-card {
            background-color: #f7fee7;
            border: 1px solid #d9f99d;
            box-shadow: 0 20px 25px -5px rgba(0, 0, 0, 0.1), 0 8px 10px -6px rgba(0, 0, 0, 0.05);
        }
        .custom-select-wrapper select {
            -webkit-appearance: none;
            -moz-appearance: none;
            appearance: none;
        }
        @media (max-width: 639px) { 
            .card-content-wrapper { flex-direction: column; align-items: center; padding: 1.5rem !important; }
            .card-image-and-text { flex-direction: column; align-items: center; width: 100%; order: 0; }
            .card-image-and-text .w-32 { margin-right: 0; margin-bottom: 1rem; }
            .card-content-text { text-align: center; }
            .card-content-wrapper > * { width: 100%; }
        }
    </style>
</head>
<body>
    <div id="directory-app-container" class="bg-slate-50 max-w-6xl mx-auto px-4 sm:px-6 lg:px-8 py-16">

        <header class="mb-12 text-center border-b border-gray-100 pb-10">
            <h1 class="text-5xl font-extrabold text-slate-800">
                🌟 The Ultimate Quilt Resource Hub
            </h1>
            <p class="mt-4 text-xl text-slate-600">
                The ultimate directory for finding **quilt resources, guilds, and stores** around the world.
            </p>
            <div class="mt-8">
                <div class="flex justify-center items-center flex-wrap gap-4 mb-4">
                    <a href="https://forms.gle/ETwmFDwBdV3yDk2M9" target="_blank" rel="noopener noreferrer" id="submit-button" class="inline-flex items-center px-8 py-3 border border-transparent text-lg font-semibold rounded-full shadow-lg text-white bg-primary-500 hover:bg-primary-600 transition duration-300 transform hover:scale-[1.02]" style="color: white;">
                        <svg class="w-6 h-6 mr-3 -ml-1" xmlns="http://www.w3.org/2000/svg" fill="none" viewbox="0 0 24 24" stroke="currentColor">
                            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M12 6v6m0 0v6m0-6h6m-6 0H6"></path>
                        </svg>
                        Submit a Resource!
                    </a>
                </div>

                <p class="mt-4 text-sm text-slate-500">
                    Need to update your listing? Just resubmit the form and we'll take care of it.
                </p>

            </div>
        </header>
        
        <div id="member-profile-view" class="hidden mb-16"></div>

        <div class="mb-10 flex flex-col sm:flex-row gap-4">
            
            <div class="relative rounded-xl shadow-lg border border-gray-200 flex-grow">
                <div class="absolute inset-y-0 left-0 pl-4 flex items-center pointer-events-none">
                    <svg class="h-6 w-6 text-gray-400" xmlns="http://www.w3.org/2000/svg" viewbox="0 0 20 20" fill="currentColor" aria-hidden="true">
                        <path fill-rule="evenodd" d="M8 4a4 4 0 100 8 4 4 0 000-8zM2 8a6 6 0 1110.89 3.476l4.817 4.817a1 1 0 01-1.414 1.414l-4.816-4.816A6 6 0 012 8z" clip-rule="evenodd"></path>
                    </svg>
                </div>
                <input type="text" name="search" id="search-input" class="focus:ring-2 focus:ring-offset-2 focus:ring-primary-500 focus:border-primary-500 block w-full pl-12 pr-4 sm:text-lg border-gray-300 rounded-xl py-4 transition duration-300" placeholder="Search by name, category, location, etc...">
            </div>

            <div class="relative w-full sm:w-64">
                <label for="sort-style" class="block text-sm font-medium text-gray-700 mb-1">Filter/Sort Category</label>
                <div class="relative custom-select-wrapper">
                    <select id="sort-style" class="block w-full rounded-xl border-gray-300 shadow-xl bg-white focus:ring-2 focus:ring-offset-2 focus:ring-primary-500 py-4 pl-4 pr-10 transition duration-300 text-base cursor-pointer">
                    </select>
                    <div class="absolute inset-y-0 right-0 top-0 pr-3 flex items-center pointer-events-none h-full">
                        <svg class="h-5 w-5 text-gray-400" xmlns="http://www.w3.org/2000/svg" viewbox="0 0 20 20" fill="currentColor"><path fill-rule="evenodd" d="M10 3a1 1 0 01.707.293l3 3a1 1 0 01-1.414 1.414L10 5.414l-2.293 2.293a1 1 0 01-1.414-1.414l3-3A1 1 0 0110 3zm-3.707 9.293a1 1 0 011.414 0L10 14.586l2.293-2.293a1 1 0 011.414 1.414l-3 3a1 1 0 01-1.414 0l-3-3a1 1 0 010-1.414z" clip-rule="evenodd"></path></svg>
                    </div>
                </div>
            </div>
        </div>

        <div id="loading-state" class="text-center py-20">
            <p id="loading-text" class="text-xl text-gray-500">Loading directory...</p>
        </div>

        <div id="error-message" class="hidden bg-red-50 border border-red-300 text-red-700 px-6 py-4 rounded-lg relative mb-10 shadow-md" role="alert">
            <strong class="font-bold">🚨 Error!</strong>
            <span class="block sm:inline" id="error-text"></span>
        </div>

        <div id="directory-grid" class="grid grid-cols-1 gap-8"></div>

    </div>
</body>
    <script async defer src="https://maps.googleapis.com/maps/api/js?key=AIzaSyAGpSoy_e59rC8oO-VG1CMOZeL--q6-8Ek&libraries=places"></script>

    <script>
        // *** FINAL, CORRECTED CONFIGURATION ***
        const GOOGLE_SHEET_URL = 'https://api.sheetbest.com/sheets/16388a5d-5336-41bf-8ab4-a2a1137ca0a3';
        const GOOGLE_FORM_URL = 'https://forms.gle/ETwmFDwBdV3yDk2M9'; 
        const GOOGLE_MAPS_API_KEY = 'AIzaSyAGpSoy_e59rC8oO-VG1CMOZeL--q6-8Ek';

        (function() {

            let allEntries = [];

            // --- RESOURCE CATEGORIES (Used for the filter dropdown) ---
            const RESOURCE_CATEGORIES = [
                'All Resources (A-Z Name)', 
                'Quilt Guilds', 'Local Quilt Store', 'Online Quilt Store', 'Quilt Shows', 
                'Professional Organisations', 'Quilt Pattern Designers', 'Quilt Teachers & Educators', 
                'Longarm Services', 'Fiber Art Galleries',
            ];
            let currentSortStyle = RESOURCE_CATEGORIES[0];

            // *** CRITICAL: Exact Column Header Mapping from your Google Sheet ***
            const NAME_KEY = 'Resource/Business Name:';
            const CATEGORY_KEY = 'Resource Type/Category:';
            const LOCATION_KEY = 'Full Location (City, State/Province, Country):';
            const EMAIL_KEY = 'Contact Email Address:';
            const WEBSITE_KEY = 'Website URL (or Etsy/Blog):';
            const INSTAGRAM_KEY = 'Instagram Handle:';
            const FACEBOOK_KEY = 'Facebook Page URL:';
            const PHOTO_KEY = 'Logo or Profile Photo:';
            const BIO_KEY = 'Brief Description / Bio:';
            const TIMESTAMP_KEY = 'Timestamp'; 
            
            let styleColumnKey = CATEGORY_KEY; 

            document.addEventListener('DOMContentLoaded', () => {
                const searchInput = document.getElementById('search-input');
                searchInput.addEventListener('input', handleSearch);

                fetchDirectoryData();
            });
            
            function populateSortDropdown() {
                const dropdown = document.getElementById('sort-style');
                dropdown.innerHTML = RESOURCE_CATEGORIES.map(category => 
                    `<option value="${category}" ${category === currentSortStyle ? 'selected' : ''}>${category}</option>`
                ).join('');
                
                dropdown.addEventListener('change', handleSort);
            }
            
            function handleSort(event) {
                currentSortStyle = event.target.value;
                applySortAndFilter(document.getElementById('search-input').value);
            }

            async function fetchDirectoryData() {
                const grid = document.getElementById('directory-grid');
                const loading = document.getElementById('loading-state');
                const errorContainer = document.getElementById('error-message');

                grid.innerHTML = '';
                errorContainer.classList.add('hidden');
                loading.classList.remove('hidden');

                try {
                    const response = await fetch(GOOGLE_SHEET_URL);
                    if (!response.ok) {
                        throw new Error(`Failed to fetch data. Status: ${response.status}`);
                    }
                    
                    // Reading as JSON for Sheet Best API
                    const data = await response.json(); 
                    
                    const validData = data.filter(entry => entry[NAME_KEY] && entry[NAME_KEY].trim() !== '');
                    allEntries = validData;
                    
                    if (allEntries.length > 0 && !allEntries[0].hasOwnProperty(CATEGORY_KEY)) {
                         console.warn(`Could not find the expected category column: ${CATEGORY_KEY}.`);
                    }

                    populateSortDropdown();
                    applySortAndFilter(''); 

                } catch (error) {
                    console.error('Error fetching directory data:', error);
                    // Shows the Sheet Best API URL must be wrong or the sheet isn't shared/verified
                    showError(`Failed to load directory. Data access failed: ${error.message}. Please verify your Sheet Best API link and Google Sheet permissions.`);
                } finally {
                    loading.classList.add('hidden');
                }
            }
            
            function applySortAndFilter(query) {
                const filteredBySearch = allEntries.filter(entry => {
                    if (!query) return true;
                    const searchableText = Object.values(entry)
                        .join(' ')
                        .toLowerCase();
                    return searchableText.includes(query.toLowerCase().trim());
                });

                let sortedEntries = [...filteredBySearch];

                if (currentSortStyle === RESOURCE_CATEGORIES[0]) {
                    sortedEntries.sort((a, b) => {
                        return (a[NAME_KEY] || '').toLowerCase().localeCompare((b[NAME_KEY] || '').toLowerCase());
                    });
                } else {
                    const targetCategory = currentSortStyle.toLowerCase()
                                            .replace(/store|guilds|shows|organisations|designers|educators|services|galleries/g, '')
                                            .trim();
                    
                    sortedEntries.sort((a, b) => {
                        const styleA = (a[CATEGORY_KEY] || '').trim().toLowerCase();
                        const styleB = (b[CATEGORY_KEY] || '').trim().toLowerCase();

                        const aMatches = styleA.includes(targetCategory);
                        const bMatches = styleB.includes(targetCategory);

                        if (aMatches && !bMatches) return -1;
                        if (!aMatches && bMatches) return 1;

                        return (a[NAME_KEY] || '').toLowerCase().localeCompare((b[NAME_KEY] || '').toLowerCase());
                    });
                    
                    sortedEntries = sortedEntries.filter(entry => {
                         return (entry[CATEGORY_KEY] || '').trim().toLowerCase().includes(targetCategory);
                    });
                }

                renderDirectory(sortedEntries);
            }

            function handleSearch(event) {
                applySortAndFilter(event.target.value);
            }

            function renderDedicatedProfile(entry) {
                let profileView = document.getElementById('member-profile-view');
                const renderedCard = renderSingleCard(entry, true);
                const location = entry[LOCATION_KEY]; 

                let mapHTML = '';
                
                if (location && location.trim()) {
                    const encodedLocation = encodeURIComponent(location);
                    const staticMapUrl = `https://maps.googleapis.com/maps/api/staticmap?center=${encodedLocation}&zoom=10&size=700x250&maptype=roadmap&markers=color:red%7Clabel:Q%7C${encodedLocation}&key=${GOOGLE_MAPS_API_KEY}`;
                    const liveMapUrl = `https://www.google.com/maps/search/?api=1&query=${encodedLocation}`;

                    mapHTML = `
                        <div class="mt-8 border border-gray-200 rounded-xl p-6 bg-white shadow-lg">
                            <h3 class="text-2xl font-bold text-gray-900 mb-4 flex items-center">
                                <svg class="w-6 h-6 mr-3 text-red-500" fill="currentColor" viewBox="0 0 20 20" xmlns="http://www.w3.org/2000/svg"><path fill-rule="evenodd" d="M5.05 4.05a7 7 0 119.9 9.9L10 18.9l-4.95-4.95a7 7 0 010-9.9zM10 11a2 2 0 100-4 2 2 0 000 4z" clip-rule="evenodd"></path></svg>
                                Location
                            </h3>
                            <a href="${liveMapUrl}" target="_blank" rel="noopener noreferrer" class="block rounded-xl overflow-hidden border-2 border-gray-300 hover:border-primary-500 transition-all duration-300 shadow-md" aria-label="View ${escapeHTML(location)} on Google Maps">
                                <img
                                    src="${staticMapUrl}"
                                    alt="Map preview for ${location}"
                                    class="w-full h-auto object-cover"
                                >
                            </a>
                            <p class="mt-3 text-sm text-gray-500">
                                Location: **${escapeHTML(location)}**. Click the map to view the live location on Google Maps.
                            </p>
                        </div>
                    `;
                }

                profileView.innerHTML = `
                    <div class="mb-6 border-b pb-4 border-gray-200">
                        <h2 class="text-3xl font-bold text-slate-800 mb-2">Detailed Profile: ${escapeHTML(entry[NAME_KEY])}</h2>
                        <button id="close-profile-btn" class="text-md text-primary-600 hover:text-primary-800 font-medium flex items-center transition duration-200">
                            <svg class="w-4 h-4 mr-1" fill="none" viewBox="0 0 24 24" stroke="currentColor"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M10 19l-7-7m0 0l7-7m-7 7h18"></path></svg>
                            Back to Directory
                        </button>
                    </div>
                    <div class="bg-white rounded-xl shadow-2xl overflow-hidden border border-gray-200">
                        ${renderedCard}
                    </div>
                    ${mapHTML}
                `;

                document.getElementById('close-profile-btn').addEventListener('click', (e) => {
                    e.preventDefault();
                    document.getElementById('member-profile-view').classList.add('hidden');
                    document.getElementById('directory-app-container').scrollIntoView({ behavior: 'smooth' });
                });
            }


            function renderDirectory(data) {
                const grid = document.getElementById('directory-grid');
                grid.innerHTML = '';

                const filteredData = data.filter(entry => (entry[NAME_KEY] || '').trim() !== '');

                if (filteredData.length === 0) {
                    const searchInput = document.getElementById('search-input');
                    const message = searchInput && searchInput.value.trim() !== '' ? 'No entries match your search. Try a different query or category.' : 'No directory entries found.';
                    grid.innerHTML = `<p class="text-gray-500 text-center col-span-full py-10">${message}</p>`;
                    return;
                }

                filteredData.forEach(entry => {
                    grid.innerHTML += renderSingleCard(entry);
                });
                
                document.querySelectorAll('.member-profile-link').forEach(link => {
                    link.addEventListener('click', function(e) {
                        e.preventDefault();
                        const entry = allEntries.find(e => e[NAME_KEY] === this.dataset.memberName);
                        if (entry) {
                            renderDedicatedProfile(entry);
                            document.getElementById('member-profile-view').classList.remove('hidden');
                            document.getElementById('member-profile-view').scrollIntoView({ behavior: 'smooth' });
                        }
                    });
                });
            }


            function renderSingleCard(entry, isDedicatedProfile = false) {
                const primaryFields = [NAME_KEY, BIO_KEY, EMAIL_KEY, TIMESTAMP_KEY];
                
                const { imageUrl } = findImageUrl(entry, PHOTO_KEY);
                
                const location = entry[LOCATION_KEY]; 
                const encodedLocation = location ? encodeURIComponent(location) : '';
                const liveMapUrl = encodedLocation ? `https://www.google.com/maps/search/?api=1&query=${encodedLocation}` : '#';

                let otherInfoHTML = '';
                
                const renderField = (key, value) => {
                    let href = value.trim(); let displayValue = value; let iconHtml = ''; let isLink = false;
                    const isInstagramField = key === INSTAGRAM_KEY; const isWebsiteField = key === WEBSITE_KEY; const isFacebookField = key === FACEBOOK_KEY; 

                    if (isInstagramField) {
                        href = createInstagramUrl(value); isLink = true;
                        iconHtml = `<svg class="w-4 h-4 mr-1.5 text-gray-400 group-hover:text-primary-600" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><rect x="2" y="2" width="20" height="20" rx="5" ry="5"></rect><path d="M16 11.37A4 4.4 0 0 1 12 16a4 4 0 0 1-4-4 4 4 0 0 1 4-4 4 4 0 0 1 4 4z"></path><line x1="17.5" y1="6.5" x2="17.51" y2="6.5"></line></svg>`;
                        displayValue = value.startsWith('@') ? value : '@' + value;
                    } else if (isWebsiteField || isFacebookField) {
                        if (href.startsWith('www.')) { href = 'https://' + href; } else if (!href.startsWith('http')) { href = 'https://' + href; }
                        isLink = true;
                        iconHtml = isFacebookField ? `<svg class="w-4 h-4 mr-1.5 text-gray-400 group-hover:text-primary-600" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="currentColor"><path d="M22 12c0-5.52-4.48-10-10-10S2 6.48 2 12c0 4.84 3.44 8.87 8 9.8V15h-2V13h2v-2c0-2.2 1.08-3 3-3 0.88 0 1.68 0.16 2 0.22V8h-2c-1.1 0-2 0.9-2 2v1h3l-0.5 2h-2.5v6.8c4.56-0-8-4.96 8-9.8V12z"/></svg>` : `<svg class="w-4 h-4 mr-1.5 text-gray-400 group-hover:text-primary-600" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 20 20" fill="currentColor" aria-hidden="true"><path d="M12.232 4.232a2.5 2.5 0 013.536 0l1.5 1.5a2.5 2.5 0 01-3.536 3.536l-1.5-1.5a2.5 2.5 0 010-3.536z" /><path d="M7.768 15.768a2.5 2.5 0 01-3.536 0l-1.5-1.5a2.5 2.5 0 013.536-3.536l1.5 1.5a2.5 2.5 0 010 3.536z" /><path d="M13.5 6.5a.5.5 0 00-.707-.707l-4 4a.5.5 0 00.707.707l4-4z" /></svg>`;
                    displayValue = value;
                } else if (isWebUrl(value)) { 
                        if (href.startsWith('www.')) { href = 'https://' + href; }
                        iconHtml = `<svg class="w-4 h-4 mr-1.5 text-gray-400 group-hover:text-primary-600" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 20 20" fill="currentColor" aria-hidden="true"><path d="M12.232 4.232a2.5 2.5 0 013.536 0l1.5 1.5a2.5 2.5 0 01-3.536 3.536l-1.5-1.5a2.5 2.5 0 010-3.536z" /><path d="M7.768 15.768a2.5 2.5 0 01-3.536 0l-1.5-1.5a2.5 2.5 0 013.536-3.536l1.5 1.5a2.5 2.5 0 010 3.536z" /><path d="M13.5 6.5a.5.5 0 00-.707-.707l-4 4a.5.5 0 00.707.707l4-4z" /></svg>`;
                        isLink = true;
                }

                let valueHTML = '';
                if (isLink) { valueHTML = `<a href="${href}" target="_blank" rel="noopener noreferrer" class="inline-flex items-center text-primary-600 hover:text-primary-700 hover:underline group font-medium transition duration-200">${iconHtml}${escapeHTML(displayValue)}</a>`; } 
                else { valueHTML = escapeHTML(value); if (key === BIO_KEY && value.length < 100) { valueHTML += '<br> '; } }
                
                return `<div class="py-3 sm:grid sm:grid-cols-3 sm:gap-4 px-6"><dt class="text-sm font-medium text-gray-500">${escapeHTML(key)}</dt><dd class="text-sm text-gray-800 mt-1 sm:mt-0 sm:col-span-2 break-words">${valueHTML}</dd></div>`;
            };

            if (entry[INSTAGRAM_KEY]) { instaHtml = renderField(INSTAGRAM_KEY, entry[INSTAGRAM_KEY]); }
            if (entry[WEBSITE_KEY]) { websiteHtml = renderField(WEBSITE_KEY, entry[WEBSITE_KEY]); }
            if (entry[FACEBOOK_KEY]) { facebookHtml = renderField(FACEBOOK_KEY, entry[FACEBOOK_KEY]); }

            const exclusionKeys = new Set([...primaryFields, INSTAGRAM_KEY, WEBSITE_KEY, FACEBOOK_KEY, LOCATION_KEY, PHOTO_KEY, 'Submitter\'s Name (for verification only):', 'Agreement:', CATEGORY_KEY]); 
            
            Object.keys(entry).forEach(key => {
                if (exclusionKeys.has(key) || !entry[key] || key === PHOTO_KEY) return;
                genericInfoHtml += renderField(key, entry[key]);
            });

            if (instaHtml || websiteHtml || facebookHtml || genericInfoHtml) { 
                otherInfoHTML = `<div class="mt-0 border-t border-gray-100 pt-0"><dl class="divide-y divide-gray-100">${instaHtml}${websiteHtml}${facebookHtml}${genericInfoHtml}</dl></div>`;
            }
            
            const imageSizeClass = isDedicatedProfile ? 'w-48 h-48 sm:w-64 sm:h-64' : 'w-32 h-32';
            const imageMarginClass = isDedicatedProfile ? 'mb-6 sm:mr-8 sm:mb-0' : 'mr-4';
            const imageShadowClass = isDedicatedProfile ? 'shadow-xl ring-8 ring-primary-100' : 'shadow-md';

            const imageBlockHTML = `
                <div class="${imageSizeClass} aspect-square flex-shrink-0 bg-slate-100 rounded-xl overflow-hidden border border-gray-200 ${imageShadowClass} ${imageMarginClass}">
                    ${imageUrl ? `<img src="${imageUrl}" alt="Resource photo for ${escapeHTML(entry[NAME_KEY] || 'Entry')}" class="w-full h-full object-cover">` : `<div class="w-full h-full flex items-center justify-center text-gray-400 text-sm font-semibold text-center p-2"><svg class="w-10 h-10 text-gray-300" fill="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path d="M12 12c2.21 0 4-1.79 4-4s-1.79-4-4-4-4 1.79-4 4 1.79 4 4 4zm0 2c-2.67 0-8 1.34-8 4v2h16v-2c0-2.66-5.33-4-8-4z"></path></svg></div>`}
                </div>
            `;

            const contentBlockHTML = `
                <div class="flex-grow min-w-0 card-content-text">
                    <a href="#" data-member-name="${escapeHTML(entry[NAME_KEY])}" class="member-profile-link">
                        <h3 class="${isDedicatedProfile ? 'text-4xl' : 'text-2xl'} font-extrabold text-slate-800 mb-1 hover:text-primary-600 transition-colors duration-200 cursor-pointer">${escapeHTML(entry[NAME_KEY] || 'No Name')}</h3>
                    </a>
                    <p class="text-xl text-primary-700 font-semibold mb-3">${escapeHTML(entry[CATEGORY_KEY] || 'Quilting Resource')}</p>
                    
                    ${location && !isDedicatedProfile ? `<a href="${liveMapUrl}" target="_blank" rel="noopener noreferrer" class="text-base font-medium text-gray-500 mb-3 flex items-center hover:text-primary-600 hover:underline transition duration-200"><svg class="w-4 h-4 mr-2 text-red-400" fill="currentColor" viewBox="0 0 20 20" xmlns="http://www.w3.org/2000/svg"><path fill-rule="evenodd" d="M5.05 4.05a7 7 0 119.9 9.9L10 18.9l-4.95-4.95a7 7 0 010-9.9zM10 11a2 2 0 100-4 2 2 0 000 4z" clip-rule="evenodd"></path></svg>${escapeHTML(location)}</a>` : ''}

                    ${entry[EMAIL_KEY] ? `<a href="mailto:${escapeHTML(entry[EMAIL_KEY])}" class="inline-flex items-center text-sm font-medium text-gray-500 hover:text-primary-800 group transition duration-200"><svg class="w-4 h-4 mr-2 text-gray-400 group-hover:text-primary-800" fill="currentColor" viewBox="0 0 20 20" xmlns="http://www.w3.org/2000/svg"><path d="M2.003 5.884L10 11.884l7.997-6M2 18h16V6l-8 5-8-5v12z"></path></svg>${escapeHTML(entry[EMAIL_KEY])}</a>` : ''}
                </div>
            `;

            const cardClasses = isDedicatedProfile ? 'p-8 sm:p-10' : 'p-5 sm:p-6';

            return `
                <div class="bg-white rounded-xl shadow-lg overflow-hidden border border-gray-200 ${!isDedicatedProfile ? 'hover:shadow-xl' : ''} transition-all duration-300 ease-in-out flex flex-col min-h-full">
                    <div class="flex-grow flex card-content-wrapper ${cardClasses} ${isDedicatedProfile ? 'flex-col sm:flex-row' : ''}">
                        <div class="flex items-start flex-grow card-image-and-text">
                            ${imageBlockHTML}
                            ${contentBlockHTML}
                        </div>
                    </div>
                    ${otherInfoHTML}
                    ${entry[TIMESTAMP_KEY] ? `<div class="px-6 sm:px-8 py-3 bg-gray-50 border-t border-gray-100"><p class="text-xs text-gray-500">Submitted: ${escapeHTML(entry[TIMESTAMP_KEY])}</p></div>` : ''}
                </div>
            `;
        }


        function createInstagramUrl(handle) {
            if (typeof handle !== 'string' || !handle.trim()) { return ''; }
            const baseUrl = 'https://www.instagram.com/';
            let cleanedHandle = handle.trim();
            if (cleanedHandle.startsWith('@')) { cleanedHandle = cleanedHandle.substring(1); }
            return baseUrl + cleanedHandle;
        }

        // We only keep the utility functions needed now that we are reading JSON
        function findImageUrl(entry, explicitImageKey) {
            let imageUrl = null;
            const value = entry[explicitImageKey];
            if (value && isImageUrl(value)) { imageUrl = value.trim(); }
            return { imageUrl };
        }

        function isImageUrl(url) {
            if (typeof url !== 'string' || !url) { return false; }
            return url.startsWith('http') && /\.(jpg|jpeg|png|gif|webp|googleusercontent\.com)$/i.test(url);
        }

        function isWebUrl(url) {
            if (typeof url !== 'string' || !url) { return false; }
            return /^(https?:\/\/|www\.)/i.test(url.trim());
        }

        function showError(message) {
            const errorContainer = document.getElementById('error-message');
            const errorText = document.getElementById('error-text');
            errorText.textContent = message;
            errorContainer.classList.remove('hidden');
            document.getElementById('loading-state').classList.add('hidden');
        }

        function escapeHTML(str) {
            if (typeof str !== 'string' || str === null) { return str; }
            return str.replace(/[&<>"']/g, function(match) {
                return { '&': '&', '<': '<', '>': '>', '"': '"', "'": ''' }[match];
            });
        }

        })();
    </script>
</html>
