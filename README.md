# 🎬 YouTube Grid Layout Changer

> A simple Chrome extension that automatically adjusts YouTube's grid layout based on your screen size for the best viewing experience.

---

## 📥 Installation

1. Open Chrome and navigate to `chrome://extensions/`
2. Enable **Developer mode** (toggle in the top right corner)
3. Click **"Load unpacked"**
4. Select the folder containing these extension files
5. Done! The extension is now active on YouTube

---

## 🎯 What it does

This extension overrides the `--ytd-rich-grid-items-per-row` CSS variable on YouTube to control how many videos are displayed per row in the grid layout.

✨ **The extension automatically adjusts the grid based on your screen size!**

### 📐 Automatic Responsive Layout:

| Screen Width | Videos Per Row |
|--------------|----------------|
| Up to 767px (Mobile) | 1 video |
| 768px - 1023px (Tablet) | 2 videos |
| 1024px - 1365px | 3 videos |
| 1366px+ | 4 videos |

> The grid automatically adjusts when you resize your browser window or use different monitors!
>
> **Note:** 4 videos per row provides a clean, balanced layout. If you want more videos (5-6) on ultra-wide monitors, you can easily adjust the values in `styles.css`!

---

## ⚙️ Customization

### 💡 Want different values? You can edit the `styles.css` file!

The extension comes with responsive breakpoints that work great for most users, but you can customize them to your preference.

### How to customize the breakpoints:

1. 📝 Open `styles.css` in any text editor
2. 🔢 Modify the values in the existing breakpoints. For example, to show 5-6 videos on ultra-wide screens, change:
   ```css
   /* Extra large screens (1600px to 1919px) */
   @media (min-width: 1600px) {
       ytd-rich-grid-renderer {
           --ytd-rich-grid-items-per-row: 5 !important;  /* Change from 4 to 5 */
       }
   }

   /* Ultra wide screens (1920px and above) */
   @media (min-width: 1920px) {
       ytd-rich-grid-renderer {
           --ytd-rich-grid-items-per-row: 6 !important;  /* Change from 4 to 6 */
       }
   }
   ```
3. 💾 Save the file
4. 🔄 Go to `chrome://extensions/` and click the **reload icon** on this extension
5. ✨ Refresh YouTube to see the changes

### 🎨 Want a fixed value instead?

If you prefer the same number of videos on all screen sizes, replace the entire `styles.css` content with:

```css
ytd-rich-grid-renderer {
    --ytd-rich-grid-items-per-row: 5 !important;
}
```

Replace `5` with your preferred number.

---

## 📁 Files

| File | Description |
|------|-------------|
| `manifest.json` | Extension configuration |
| `styles.css` | **CSS with responsive breakpoints (customize this!)** |
| `icon*.png` | Extension icons |
| `README.md` | This file |

---

## 🚀 Usage

Once installed, just visit [YouTube.com](https://youtube.com) and the grid will automatically adjust based on your screen size. Try resizing your browser window to see it adapt in real-time!

---

## 📝 License

Free to use and modify as you wish!
