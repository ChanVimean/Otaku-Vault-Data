#### Proposed README.md

# 御宅宝库 - Otaku Vault

Welcome to the official data repository for **Otaku Vault (御宅宝库)**. This repository serves as a centralized JSON source for anime and donghua merchandise, designed both `Mobile` and `Website`. Developed has demo **JSON Data** in `Flutter` (_Mobile_) and `Vue` (_Website_)

## 🚀 Quick Access

You can fetch the latest data directly using the GitHub Raw URL: [https://chanvimean.github.io/Otaku-Vault-Data/index.json](https://chanvimean.github.io/Otaku-Vault-Data/index.json)

---

## 🚀 Quick Demo

- Flutter Demo (**iOS**): [https://...](https://...)
- Flutter Demo (**Android**): [https://...](https://...)
- Vue (**Website**): [https://...](https://...)

---

### Data Overview

| No. | Series                     | Character / Item              | Category       |
| :-- | :------------------------- | :---------------------------- | :------------- |
| 1   | **Spy x Family**           | `Loid` & `Yor` (Twilight Set) | _Figure_ (Set) |
| 2   | **Jujutsu Kaisen**         | `Satoru Gojo` (Infinite)      | _Figure_       |
| 3   | **Sword of Coming**        | Book 1: Special Hardcover     | _Comic_        |
| 4   | **Berserk**                | Deluxe Edition Vol. 1         | _Comic_        |
| 5   | **Demon Slayer**           | `Zenitsu` (Godspeed)          | _Figure_       |
| 6   | **Sword of Coming**        | `Ning Yao`                    | _Statue_       |
| 7   | **Jade Dynasty**           | `Xiao Bai`                    | _Statue_       |
| 8   | **Throne of Seal**         | `Sheng Cai'er `               | _Statue_       |
| 9   | **Solo Leveling**          | Manhwa Vol. 10                | _Comic_        |
| 10  | **Ne Zha 2**               | `Ne Zha` (Adult Form)         | _Figure_       |
| 11  | **Solo Leveling**          | `Sung Jinwoo`                 | _Figure_       |
| 12  | **One-Punch Man**          | `Saitama` (Serious)           | _Statue_       |
| 13  | **BTTH**                   | `Queen Medusa`                | _Figure_       |
| 14  | **Chainsaw Man**           | `Makima`                      | _Figure_       |
| 15  | **Blue Lock**              | Volume 28 (Neo-Egoist)        | _Comic_        |
| 16  | **Attack on Titan**        | `Levi Ackerman`               | _Figure_       |
| 17  | **Cyberpunk**              | `David`, `Lucy`, `Rebecca`    | _Figure_ (Set) |
| 18  | **Renegade Immortal**      | `Wang Lin`                    | _Statue_       |
| 19  | **The Apothecary Diaries** | Volume 13 (Special Ed.)       | _Comic_        |
| 20  | **Vagabond**               | VizBig Edition Vol. 1         | _Comic_        |

---

### 🛠 Data Schema

The [`index.json`](index.json) file contains an array of product objects. Below is the specification for each field:

| No. | Field            | Data Type | ENUM (Optional) & Use Case                 | Value Example                                |
| :-- | :--------------- | :-------- | :----------------------------------------- | :------------------------------------------- |
| 1   | **\_id**         | `String`  | Unique ID                                  | "fig-001"                                    |
| 2   | **id**           | `Int`     | Auto Increment                             | 1                                            |
| 3   | **name**         | `String`  | -                                          | "Wei Wuxian: Yi Ling Lao Zu Ver."            |
| 4   | **description**  | `String`  | -                                          | ""                                           |
| 5   | **series_title** | `String`  | -                                          | "The Untamed (Mo Dao Zu Shi)"                |
| 6   | **origin_type**  | `String`  | 'Donghua' 'Manga', 'Novel', 'Comic']       | "Donghua"                                    |
| 7   | **characters**   | `Array`   | -                                          | ["Wei Wuxian"]                               |
| 8   | **category**     | `Array`   | ['Figure', 'Comic', 'Statue']              | ["Figure"]                                   |
| 9   | **manufacturer** | `String`  | -                                          | "Good Smile Company"                         |
| 10  | **price**        | `Double`  | -                                          | 185.99                                       |
| 11  | **currency**     | `String`  | -                                          | "USD"                                        |
| 12  | **scale**        | `String`  | -                                          | "1/8"                                        |
| 13  | **material**     | `Array`   | -                                          | ["PVC & ABS"]                                |
| 14  | **status**       | `String`  | ['Unavailable', 'Pre-order', 'Available',] | "Pre-order"                                  |
| 15  | **release_date** | `Date`    | ISO Date (YYYY-MM-DD)                      | "2026-05-15"                                 |
| 16  | **thumbnails**   | `String`  | Aspect Ratio Squire or Similar             | "https://.../[uuid]"                         |
| 17  | **image**        | `Array`   | -                                          | ["https://.../[uuid]", "https://.../[uuid]"] |
| 18  | **tags**         | `Array`   | -                                          | ["cultivation", "fantasy", "limited"]        |

<br>

#### 🖼️ Asset Deployment: The "GitHub-as-a-CDN" Cheat

> [!Note]
> **Key Rule for images**: Use the **Raw** URL format.
>
> Example Link:
> [https://raw.githubusercontent.com/Github-Username/Otaku-Vault-Data/master/images/xiao-yan-btth.png](https://raw.githubusercontent.com/Github-Username/Otaku-Vault-Data/master/images/xiao-yan-btth.png)
>
> ##### 🚀 How it Works
>
> When you upload images to your repository, GitHub provides two types of links. To display images in your **Flutter** or **Vue** app, you must use the **Raw** version to bypass the GitHub website UI.
>
> - **Standard (Web UI)**: https://github.com/.../blob/master/images/medusa.png
> - **Raw (Direct File)**: https://raw.githubusercontent.com/.../master/images/medusa.png
>
> ##### 🔗 The Link Architecture
>
> The "Cheat Code" is a simple URL pattern:
> `https://raw.githubusercontent.com/` + `[User]` + `/` + `[Repo]` + `/` + `[Branch]` + `/` + `[Path]`

### JSON Data Structure - Example

```json
{
  "_id": "set-sxf-001",
  "id": 1,
  "name": "Spy x Family: The Forgers (Full Family Pack + Bond)",
  "description": "The complete undercover family in one premium 1/4 scale set. Includes Loid, Yor, Anya, and Bond Forger. Features a massive diorama base of the Forger living room with high-detail furniture and translucent window effects.",
  "series_title": "Spy x Family",
  "origin_type": ["Anime"],
  "characters": ["Loid Forger", "Yor Forger", "Anya Forger", "Bond Forger"],
  "category": ["Figure", "Set"],
  "manufacturer": "F:NEX",
  "price": 1450.0,
  "currency": "USD",
  "scale": "1/4",
  "material": ["Polystone", "PVC", "ABS"],
  "status": "Pre-order",
  "release_date": "2026-12-25",
  "thumbnail": "https://raw.githubusercontent.com/ChanVimean/Otaku-Vault-Data/master/images/set-sxf-001-0.png",
  "images": [
    "https://raw.githubusercontent.com/ChanVimean/Otaku-Vault-Data/master/images/set-sxf-001-1.png",
    "https://raw.githubusercontent.com/ChanVimean/Otaku-Vault-Data/master/images/set-sxf-001-2.png",
    "https://raw.githubusercontent.com/ChanVimean/Otaku-Vault-Data/master/images/set-sxf-001-3.png"
  ],
  "tags": ["family-pack", "bond", "spy-x-family", "waku-waku"]
}
```

---

### 🎨 UI Note

To keep the aesthetic consistent with the Otaku Vault brand, it is recommended to use the [**Poppins**](https://fonts.google.com/specimen/Poppins) font for all headers and clean, high-resolution product images for the grid view.

---

## 💻 Integration Examples

#### Vue.js (Fetching with Fetch API)

```js
const fetchData = async () => {
  const response = await fetch(
    "https://raw.githubusercontent.com/.../index.json",
  );
  const data = await response.json();
  return data;
};
```

---

#### Flutter (Model Definition)

Use package [`http`](https://pub.dev/packages/http/install) for fetching.

```dart
class Product {
  final String id;
  final double price;
  final List<String> characters;
  // ... other fields

  Product.fromJson(Map<String, dynamic> json)
      : id = json['id'],
        price = (json['price'] as num).toDouble(), // Safely handle Int/Double
        characters = List<String>.from(json['characters']);
}
```
