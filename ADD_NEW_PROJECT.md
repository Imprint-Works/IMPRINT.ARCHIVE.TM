# How to Add a New Project to Imprint Archive

## Complete Automation Workflow

This process is designed to be **fully automated**. You fill in the Google Sheet with 4 pieces of info, and I instantly generate everything!

---

## Step 0: Set Up Your Google Sheet (One-Time Setup)

1. Go to [sheets.google.com](https://sheets.google.com)
2. Click **"+ New"** → **"Google Sheet"**
3. Go to **File** → **Import** → **Upload**
4. Select `PROJECT_TEMPLATE.csv` from your portfolio folder
5. Click **"Import data"**
6. ✅ Done! Your automation template is ready

---

## Step 1: What You Need (Only 4 Columns!)

Add a new row to your Google Sheet with these 4 pieces of info:

| Column | What It Is | Example |
|--------|-----------|---------|
| **Project Name** | Project identifier (snake_case) | `Digital_Dreams` |
| **Project Description** | Subtitle/tagline | `A collection of digital art` |
| **Background Image File** | Path to image | `images/digital_dreams/dreams.jpg` |
| **Shopify Embed Code** | **FULL** Shopify code block | See Step 2 ↓ |

---

## Step 2: Get Your Shopify Embed Code

1. Go to **Shopify Admin** → **Sales Channels** → **Buy Button**
2. Create your collection's Buy Button
3. Click **Embed** to get the code
4. Copy the **ENTIRE** code (from `<div>` to `</script>`)
5. Paste into the **"Shopify Embed Code"** column

**Example code:**
```html
<div id='collection-component-1771234567890'></div>
<script type="text/javascript">
/*<![CDATA[*/
(function () {
  var scriptURL = 'https://sdks.shopifycdn.com/buy-button/latest/buy-button-storefront.min.js';
  ...full code...
})();
/*]]>*/
</script>
```

---

## Step 3: Prepare Your Image

1. Create: `/images/your_project_name/`
2. Save your background image there (80% opacity is nice!)
3. Path must match what you put in the spreadsheet

---

## Step 4: Tell Me!

**You say:** "Ready to add Digital_Dreams"

**I do automatically:**
- ✅ Create the project directory
- ✅ Add new section to `index.html` with your embed code
- ✅ Everything is live!

---

## That's It!

No more creating `.js` files or worrying about templates. Just:

1. Fill in 4 columns in your Google Sheet
2. Save your image file
3. Tell me the project name
4. Done! 🚀

### Required Information:

1. **Project Name** (e.g., `City_of_God`)
   - Use snake_case format (underscores instead of spaces)

2. **Project Description** (e.g., `vibrant creative projects celebrating bold artistic vision`)
   - This appears as the subtitle on your portfolio

3. **Shopify Collection ID** (e.g., `430126858473`)
   - Get this from your Shopify "Buy Button" embed code
   - Look for `"id": "XXXXXXXXXXXXX"`

4. **Component ID** (e.g., `collection-component-1771192156617`)
   - This is the unique div ID from Shopify
   - Format: `collection-component-` followed by a number

5. **Background Image File** (e.g., `images/city_of_god/citygod.jpg`)
   - Path where your image will be stored
   - Place the actual image file in the correct folder before telling me

6. **Button Text** (usually `View product`)
   - Text that appears on product view buttons

7. **Product Grid Width** (e.g., `33.33333%`)
   - `33.33333%` = 3 products per row (like ACT_UP and City of God)
   - `25%` = 4 products per row (like MESHD and OLLIE original)

8. **Font Color** (e.g., `#42f114`)
   - Your brand accent color (hex code)

9. **Button Color (Hover)** (e.g., `#3bd912`)
   - Button hover state color (hex code)

---

## Step 2: Prepare Your Image

1. Create a folder for your project:
   ```
   /images/your_project_name/
   ```

2. Place your background image there (e.g., `citygod.jpg`)

---

## Step 3: Tell Me the Details

Once you have all the information gathered and image files ready, either:

**Option A (Easiest):** Share your Google Sheet link with me
- I can read directly from the sheet
- Perfect if you set it up ahead of time

**Option B:** Copy-paste the row from your Google Sheet
- Just highlight the row and paste it in chat

**Option C:** Tell me each value individually
- Works fine too! Just list them out
```
Project Name: Digital_Dreams
Description: A collection of digital art and design
Shopify ID: 123456789012
Component ID: collection-component-1771234567890
Image File: images/digital_dreams/dreamart.jpg
```

---

## What I'll Automatically Create

Once you provide the details, I'll generate:

✅ **Script file:** `scripts/your_project/your_project.js`
   - Contains your Shopify collection setup

✅ **index.html updates:**
   - New project section with your details
   - Background image reference
   - Shopify embed call

✅ **Directory structure:**
   Next Steps

1. **Create your Google Sheet** (see Step 0 above)
2. **Fill in project details** in the sheet
3. **Prepare your image file(s)** and put them in the correct folder
4. **Share the sheet with me** OR **tell me the project values**
5. **I'll generate everything automatically!**

---

## Quick Reference: What I Need

| Field | Example | Notes |
|-------|---------|-------|
| Project Name | `Digital_Dreams` | Use snake_case (underscores, no spaces) |
| Description | `A collection of digital art` | Appears as subtitle |
| Shopify Collection ID | `546789012345` | From Shopify embed code |
| Component ID | `collection-component-1771345678901` | From Shopify embed code |
| Image File | `images/digital_dreams/dreams.jpg` | You place the image here |
| Button Text | `View product` | Usually this |
| Grid Width | `33.33333%` | 3-per-row format |
| Font Color | `#42f114` | Your brand green (or custom) |
| Button Hover | `#3bd912` | Darker shade for hover |

---

## Example: Adding "Digital Dreams" Project

**From your Google Sheet
---

## Example: Adding "Digital Dreams" Project

**Your info:**
```
Project Name: Digital_Dreams
Description: A collection of digital art and design
Shopify Collection ID: 546789012345
Component ID: collection-component-1771345678901
Background Image: images/digital_dreams/dreams.jpg
Button Text: View product
Grid Width: 33.33333%
Font Color: #42f114
Button Hover: #3bd912
```

**I create:**
- ✅ `scripts/digital_dreams/digital_dreams.js` (Shopify setup)
- ✅ New section in `index.html` with your project
- ✅ Directory: `/images/digital_dreams/`

**You do:**
- 📁 Place `dreams.jpg` in `/images/digital_dreams/`

---

## Next Steps

1. Fill in `PROJECT_TEMPLATE.csv` with your new project info
2. Prepare your image file(s)
3. Tell me the project details
4. I'll generate everything automatically!

Need help gathering your Shopify info? Just ask! 🎨
