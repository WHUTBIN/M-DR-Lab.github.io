# M-DR-Lab.github.io
M-DR Laboratory（Marine Mechanical Dynamics and Reliability Laboratory）

from pathlib import Path
import zipfile

# Create base structure
base_path = Path("/mnt/data/M-DR-Lab.github.io")
folders = [<img width="1024" height="1024" alt="image" src="https://github.com/user-attachments/assets/a1a15ceb-cdbe-497e-af98-aceb3176c6fb" />

]
files = {
    "index.html": """
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>M-DR Laboratory</title>
  <link rel="stylesheet" href="assets/css/style.css">
</head>
<body>
  <header>
    <div style="display:flex; align-items:center;">
      <img src="assets/img/logo.png" alt="M-DR Lab Logo" height="80" style="margin-right:20px;">
      <div>
        <h1>M-DR Laboratory</h1>
        <h3>Marine Mechanical Dynamics and Reliability Laboratory</h3>
      </div>
    </div>
    <nav>
      <a href="index.html">Home</a> |
      <a href="about.html">About</a> |
      <a href="team.html">Team</a> |
      <a href="research.html">Research</a> |
      <a href="projects.html">Projects</a> |
      <a href="join.html">Join</a> |
      <a href="contact.html">Contact</a>
    </nav>
  </header>
  <main>
    <section>
      <h2>Welcome to M-DR Lab</h2>
      <p>We focus on the dynamics, durability, and reliability of marine mechanical systems.</p>
    </section>
    <section>
      <h2>Research Areas</h2>
      <ul>
        <li>Ship propulsion and mechanical transmission systems</li>
        <li>Intelligent operation and maintenance (O&M) of marine equipment</li>
        <li>Friction, lubrication, and reliability of mechanical systems</li>
        <li>Smart technologies for dredging, deep sea mining, and ship lifts</li>
        <li>Oil and gas storage, transportation, and safety risk assessment</li>
      </ul>
    </section>
    <section>
      <h2>Research Subjects</h2>
      <ol>
        <li>Sensor Monitoring Systems</li>
        <li>Dredging Vessels and Equipment</li>
        <li>Pipeline Transportation Systems</li>
        <li>Marine Shafting Systems</li>
        <li>Gearboxes</li>
        <li>Centrifugal Pumps</li>
        <li>LNG/LPG Cargo Tanks</li>
      </ol>
    </section>
  </main>
  <footer>
    <p>&copy; 2025 M-DR Laboratory. All rights reserved.</p>
  </footer>
</body>
</html>
""",
    "assets/css/style.css": """
body {
  font-family: Arial, sans-serif;
  margin: 0;
  padding: 0;
  background: white;
  color: #003366;
}
header {
  background: #0077b6;
  color: white;
  padding: 20px;
}
nav a {
  color: white;
  margin: 0 10px;
  text-decoration: none;
}
main {
  padding: 20px;
}
footer {
  text-align: center;
  padding: 10px;
  background: #f0f0f0;
  color: #333;
}
""",
    "README.md": "# M-DR Lab Website\nThis is the GitHub Pages site for the Marine Mechanical Dynamics and Reliability Laboratory (M-DR Lab)."
}

# Create folders and files
for folder in folders:
    (base_path / folder).mkdir(parents=True, exist_ok=True)

for file, content in files.items():
    with open(base_path / file, "w", encoding="utf-8") as f:
        f.write(content.strip())

# Create a zip archive for download
zip_path = "/mnt/data/M-DR-Lab.github.io.zip"
with zipfile.ZipFile(zip_path, 'w') as zipf:
    for file in base_path.rglob("*"):
        zipf.write(file, file.relative_to(base_path.parent))

zip_path
