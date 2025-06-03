# 🔺 Room: Pyramid of Pain

## 🎯 Objective
Understand the Pyramid of Pain concept and how defenders can disrupt adversaries more effectively by targeting different indicators.

---

## 📘 Key Concepts

- Developed by David J. Bianco.
- The pyramid ranks indicators from least to most effective in disrupting adversary operations.
- Higher up the pyramid = more pain for the attacker when disrupted.

---

## 🧱 Pyramid Levels (Bottom to Top)

1. **Hash Values** – Easily changed by attackers.
2. **IP Addresses** – Often rotated or dynamic.
3. **Domain Names** – Can be replaced quickly.
4. **Network/Host Artifacts** – Harder to change (e.g. file paths, registry keys).
5. **Tools** – Replacing them costs time/effort.
6. **TTPs (Tactics, Techniques & Procedures)** – Deep behavioral patterns, hardest to alter.

---

## 🧠 What I Learned

- Focusing detection efforts on **TTPs** is more effective than just blocking IPs or hashes.
- Understanding the attacker's behavior gives longer-term defense benefits.

---

## 📝 Notes

- Pyramid of Pain complements frameworks like MITRE ATT&CK.
- Analysts should correlate low-level indicators with high-level tactics.

---

## ✅ Flag (if applicable)
`THM{pyramid-pain-master}`
