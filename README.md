# Interventions Grouper

A collaborative tool for organizing students into RTI (Response to Intervention) groups by skill level. Teachers can update student skills, manage rosters, and automatically generate balanced intervention groups.

## Features

- 🎨 **Colorful, engaging design** with vibrant gradients and smooth animations
- 👥 **Group management** with automatic balancing (6 students max per group, 18–22 per teacher)
- 📊 **Skill tracking** across 20 intervention levels
- 🚫 **Conflict management** — mark students who can't be in the same group
- 💾 **Auto-save** to browser storage (works offline)
- 🔄 **Real-time sync** when hosted with database (optional)
- 📱 **Mobile friendly** and printable

## Quick Start

### Option 1: Open Locally (No Setup)
1. Download `Interventions_Grouper.html`
2. Open it in any web browser — that's it!
3. Data saves to your browser's local storage (survives page refreshes, but is device-specific)

### Option 2: Host on GitHub Pages (Team Access)
1. Fork or clone this repository
2. Go to **Settings → Pages** and enable GitHub Pages on the `main` branch
3. Share the Pages URL with your team
4. Everyone can open it in their browser; data still saves locally per device

### Option 3: Self-Host (Shared Database)
For a version where all teachers see the same data in real-time:
- Deploy this HTML file to a web server (Vercel, Netlify, etc.)
- Integrate a backend (e.g., Firebase Firestore) following the `claude.use("db")` pattern in the code
- Modify the `db.doc("rti/state")` line to connect to your database

## How to Use

1. **Set up rosters** — Each teacher enters their student names (or edit the `RAW` data in the script)
2. **Update skills** — Click a teacher's name → "Update data" → select each student's current skill level
3. **Manage conflicts** — Under "Edit roster," mark pairs of students who can't be grouped together
4. **View groupings** — Click "View RTI groupings" to see auto-balanced intervention groups
5. **Print** — Click the Print button to get a hard copy for your classroom

## Customization

### Change Teacher Names
Edit the `TEACHERS` list in the HTML (search for `const RAW=`):
```javascript
const RAW = {
  "YourTeacher1": "Student1 A,Student2 B,...",
  "YourTeacher2": "Student3 C,Student4 D,...",
};
```

### Adjust Group Size
In the code, find `Math.ceil(st.length/6)` and change `6` to your target max size.

### Change Colors
The `TC` and `CC` objects control student and column colors. Customize hex values to match your school's palette.

### Adjust Skill List
The `SK` array contains all intervention skills. Add, remove, or rename skills as needed.

## Technical Details

- **No external dependencies** — pure HTML, CSS, and JavaScript
- **Browser storage** — uses `localStorage` for persistence
- **Database-ready** — includes hooks for Claude DB or other backends
- **Print-friendly** — hides UI controls and preserves colors
- **Responsive** — works on desktop, tablet, and phone

## Troubleshooting

**Data disappeared after closing the browser?**
- Make sure you're on the same device and browser. Local storage is per-device, per-browser.

**Want to sync across devices?**
- Host it on a server and add a database backend (see Option 3 above).

**Print looks wrong?**
- Try Print Preview to adjust margins. The page is optimized for standard letter size.

## License

Free to use and modify for your school.

## Questions?

This tool was built for 2nd grade intervention planning. Adjust it to fit your grade level and skill set!
