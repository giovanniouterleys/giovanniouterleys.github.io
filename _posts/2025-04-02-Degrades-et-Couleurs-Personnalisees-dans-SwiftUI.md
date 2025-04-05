---
title: Dégradés et Couleurs Personnalisées dans SwiftUI
date: 2025-04-02 23:05:00 +0100
categories:
  - SwiftUI
  - Développement iOS
tags:
  - swiftui
  - couleurs
  - dégradés
  - design
  - interface
description: Ajoutez du style à vos interfaces SwiftUI avec des dégradés élégants et des couleurs personnalisées. Apprenez à les appliquer facilement.
---

# Dégradés et Couleurs Personnalisées dans SwiftUI

Les couleurs jouent un rôle crucial dans la construction d’interfaces attrayantes. SwiftUI permet de définir très facilement des **couleurs personnalisées** et des **dégradés**, offrant un haut niveau de personnalisation visuelle à tes vues.

Dans cet article, tu vas apprendre à :
- Utiliser les couleurs de base fournies par SwiftUI
- Créer et appliquer des **couleurs personnalisées**
- Styliser tes vues avec des **dégradés linéaires, radiaux et angulaires**

---

## 🎨 Utiliser les Couleurs SwiftUI

SwiftUI propose une large palette de couleurs système, prêtes à l'emploi.

---
```
Text("Texte coloré")
    .foregroundColor(.blue)

Rectangle()
    .fill(Color.green)
```
---

💡 Ces couleurs s’adaptent automatiquement aux **modes clair/sombre**.

### Exemples de couleurs système :
- `.red`, `.orange`, `.yellow`, `.green`, `.blue`, `.purple`, `.pink`, `.gray`
- `.primary` / `.secondary` (adaptatifs)

---

## 🧱 Créer des Couleurs Personnalisées

### 1️⃣ En dur dans le code (avec RGB) :

---
```
Color(red: 0.2, green: 0.6, blue: 0.9)
```
---

Ou en hexadécimal via une extension :

---
```
extension Color {
    static let monBleu = Color(red: 0.15, green: 0.45, blue: 0.75)
}
```
---

💡 Tu peux ensuite utiliser `Color.monBleu` dans tes vues.

---

### 2️⃣ Depuis les `Assets` de Xcode

1. Va dans `Assets.xcassets`.
2. Clique droit > New Color Set.
3. Renomme-la (ex : `BrandColor`).
4. Choisis une couleur dans l’inspecteur.

---
```
Rectangle()
    .fill(Color("BrandColor"))
```
---

![](../assets/images/2025-04-02-Degrades-et-Couleurs-Personnalisees-dans-SwiftUI/BrandColor.gif)

---

## 🌈 Créer des Dégradés

### 1️⃣ Dégradé linéaire

---
```
LinearGradient(
    colors: [.blue, .purple],
    startPoint: .top,
    endPoint: .bottom
)
.frame(height: 200)
```
---

💡 `startPoint` et `endPoint` définissent la direction du dégradé.

---

### 2️⃣ Dégradé radial

---
```
RadialGradient(
    colors: [.orange, .red],
    center: .center,
    startRadius: 20,
    endRadius: 100
)
.frame(width: 200, height: 200)
```
---

💡 Crée un **effet de halo** autour du centre.

---

### 3️⃣ Dégradé angulaire

---
```
AngularGradient(
    colors: [.yellow, .pink, .purple],
    center: .center
)
.frame(width: 200, height: 200)
.clipShape(Circle())
```
---

💡 Idéal pour des effets circulaires (ex : indicateurs d’activité, badges).

---

## 🧠 Combiner Dégradé et Texte

Tu peux utiliser un dégradé comme fond derrière un texte :

---
```
ZStack {
    LinearGradient(colors: [.blue, .green], startPoint: .leading, endPoint: .trailing)

    Text("Dégradé")
        .font(.largeTitle)
        .bold()
        .foregroundColor(.white)
}
.frame(height: 100)
.cornerRadius(12)
```

---

![](../assets/images/2025-04-02-Degrades-et-Couleurs-Personnalisees-dans-SwiftUI/degrader.png)

---

## 🧩 Astuce : Dégradé sur forme masquée

Applique un dégradé dans une forme avec `mask` :

---
```
LinearGradient(colors: [.pink, .purple], startPoint: .top, endPoint: .bottom)
    .mask(
        Text("Masqué")
            .font(.system(size: 60, weight: .bold))
    )
```
---

💡 Résultat : **le texte est "rempli" avec le dégradé** au lieu d’être uni.

---

## ✅ Conclusion

Les **couleurs personnalisées** et **dégradés** sont un excellent moyen d’enrichir visuellement tes interfaces SwiftUI.  
Tu sais maintenant :
- Utiliser les couleurs système et personnalisées
- Styliser tes vues avec des dégradés linéaires, radiaux et angulaires
- Appliquer des effets avancés avec `mask` ou `clipShape()`

📌 **Prochain article : Utilisation de SF Symbols dans SwiftUI !** 🧩
