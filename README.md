#### Proposed README.md

# 御宅宝库 - Otaku Vault

Welcome to the official data repository for **Otaku Vault (御宅宝库)**. This repository serves as a centralized JSON source for anime and donghua merchandise, designed both `Mobile` and `Website`. Developed has demo **JSON Data** in `Flutter` (_Mobile_) and `Vue` (_Website_)

## 🚀 Quick Access

You can fetch the latest data directly using the GitHub Raw URL: [https://...](https://...)

---

## 🚀 Quick Demo

- Flutter Demo (**iOS**): [https://...](https://...)
- Flutter Demo (**Android**): [https://...](https://...)
- Vue (**Website**): [https://...](https://...)

---

### 🛠 Data Schema

The [`index.json`](index.json) file contains an array of product objects. Below is the specification for each field:

| No. | Field            | Data Type | ENUM (Optional)                                 | Value Example                         |
| :-- | :--------------- | :-------- | :---------------------------------------------- | :------------------------------------ |
| 1   | **\_id**         | `String`  | Unique ID                                       | "fig-001"                             |
| 2   | **id**           | `Int`     | Auto Increment                                  | 1                                     |
| 3   | **name**         | `String`  | -                                               | "Wei Wuxian: Yi Ling Lao Zu Ver."     |
| 4   | **description**  | `String`  | -                                               | ""                                    |
| 5   | **origin_type**  | `String`  | ['Anime', 'Donghua', 'Manga', 'Novel', 'Comic'] | "Donghua"                             |
| 6   | **series_title** | `String`  | -                                               | "The Untamed (Mo Dao Zu Shi)"         |
| 7   | **characters**   | `Array`   | -                                               | ["Wei Wuxian"]                        |
| 8   | **category**     | `Array`   | ['Figure', 'Manga', 'Novel', 'Comic]            | ["Figure"]                            |
| 9   | **manufacturer** | `Array`   | -                                               | ["Good Smile Company"]                |
| 10  | **price**        | `Double`  | -                                               | 185.99                                |
| 11  | **currency**     | `String`  | -                                               | "USD"                                 |
| 12  | **scale**        | `String`  | -                                               | "1/8"                                 |
| 13  | **material**     | `Array`   | -                                               | ["PVC & ABS"]                         |
| 14  | **status**       | `String`  | ['Unavailable', 'Pre-order', 'Available]        | "Pre-order"                           |
| 15  | **release_date** | `Date`    | ISO Date (YYYY-MM-DD)                           | "2026-05-15"                          |
| 16  | **images**       | `Array`   | -                                               | ["https://...", "https://..."]        |
| 17  | **tags**         | `Array`   | -                                               | ["cultivation", "fantasy", "limited"] |

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
  "_id": "fig-001",
  "id": 1,
  "name": "Wei Wuxian: Yi Ling Lao Zu Ver.",
  "origin_type": ["Donghua"],
  "series_title": "The Untamed (Mo Dao Zu Shi)",
  "characters": ["Wei Wuxian"],
  "category": ["Figure"],
  "manufacturer": ["Good Smile Company"],
  "price": 185.99,
  "currency": "USD",
  "scale": "1/8",
  "material": ["PVC & ABS"],
  "status": "Pre-order",
  "release_date": "2026-05-15",
  "images": [
    "https://store.example.com/images/wwx_01.jpg",
    "https://store.example.com/images/wwx_02.jpg"
  ],
  "tags": ["cultivation", "fantasy", "limited"]
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
