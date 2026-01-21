# 🃏 Card Creator for Card Shop Simulator

[![Made with C#](https://img.shields.io/badge/Made%20with-C%23-blue)](https://docs.microsoft.com/en-us/dotnet/csharp/) 
[![Windows Forms](https://img.shields.io/badge/GUI-Windows%20Forms-lightgrey)](https://learn.microsoft.com/en-us/dotnet/desktop/winforms/)  

A **C# Windows Forms tool** to automatically generate **Lua code** for creating or editing cards in *Card Shop Simulator* (Unreal Engine).  

This tool speeds up card creation for mods by producing ready-to-use Lua code.

---

## ⚙️ How it works

- The app generates Lua code based on the values you input.  
- Any field left empty or checkbox not checked **will not be generated** in the final Lua code.  
- After filling all the fields, click **Create or Edit Card** to generate the Lua code, which is automatically copied to your clipboard.

---

## 🆔 Card ID & Data Card

- **Card ID**: Only numbers are allowed. Corresponds to the card the player wants to **replace** or **create**.  
- **Data Card (Dxxx)**: Only numbers are allowed. Must be **unique**. Used as the Lua variable name (e.g., `D676`).

---

## 🧬 Gen (Generation)

Only **one checkbox** can be selected at a time.

| Checkbox | Lua Value |
|----------|-----------|
| Gen 0    | `D.Gen = 0` |
| Gen 1    | `D.Gen = 1` |
| Gen 2    | `D.Gen = 2` |
| Gen 3    | `D.Gen = 3` |
| Gen 4    | `D.Gen = 4` |
| Gen 5    | `D.Gen = 5` |
| Gen 6    | `D.Gen = 6` |

---

## 🖼 Texture

- Enter a valid **relative path** to the card texture: card_images/generalgrievous.png


---

## ⭐ Rarity

Only **one checkbox** can be selected at a time:

- Common  
- UnCommon  
- Rare  
- SuperRare  
- God  

---

## ⚔ Stats

| Field | Type | Example |
|-------|------|---------|
| Base Attack | Integer | `500` |
| Base Health | Integer | `750` |
| Value Multiplicator | Float | `5.0` |

---

## 🌊 Flow Settings

| Field | Type | Example |
|-------|------|---------|
| Flow Texture Path | File path | `card_images/fire.png` |
| Flow Value | 0 or 1 | `1` |
| Flow Speed X | Float | `0.1` |
| Flow Speed Y | Float | `-0.1` |

---

## 🧪 Card Element Faction

Only **one checkbox** can be selected at a time:

- Earth  
- Grass  
- Insect  
- Steel  
- Fire  
- Water  
- Mystic  
- Electric  
- Animal  
- Rock  
- Ice  
- Psychic  
- Dragon  

---

## ⚠️ Important Notes

- If a field is left empty or a checkbox is unchecked, the corresponding line **will not be created or modified** in the Lua code.

---

## ▶️ Generate Lua Code

After filling the fields:  

1. Click **Create or Edit Card**.  
2. The Lua code is:  
   - Automatically generated  
   - Formatted correctly  
   - Copied to your clipboard  
   - Ready to paste into your mod  

---

## 📝 Example Lua Output

```lua
local D676 = UE.FCardDataAll()
D676.CardID = 1101
D676.Name = "Ewok"
D676.Description = "Creature of Endor"
D676.TexturePath = dir .. "card_images/ewok.png"
D676.Gen = 0
D676.Rarity = UE.ECardRarity.Rare
D676.BaseAttack = 500
D676.BaseHealth = 450
D676.CardValueMulti = 5.0
D676.CardElementFaction:Add(UE.ECardElementFaction.Animal)
R:RegisterCardData(D676.CardID, D676)

