---
title: "Customisation avec .clipShape() et .overlay() dans SwiftUI"
date: 2025-03-26 11:00:00 +0100
categories: [SwiftUI, Développement iOS]
tags: [swiftui, customisation, clipshape, overlay, design]
description: "Maîtrisez les modificateurs `.clipShape()` et `.overlay()` pour styliser vos vues et créer des interfaces visuellement percutantes."
---

# Customisation avec `.clipShape()` et `.overlay()` dans SwiftUI

SwiftUI propose deux modificateurs ultra puissants pour styliser tes composants :  
- `.clipShape()` : pour **découper** une vue selon une forme  
- `.overlay()` : pour **superposer** un élément sur une autre vue

Dans cet article, tu vas apprendre à :
- Masquer des vues avec des formes (`Circle`, `Capsule`, `RoundedRectangle`)
- Ajouter des contours, des calques visuels ou du texte en surimpression
- Combiner les deux pour des effets d’interface modernes et dynamiques

---

## ✂️ `.clipShape()` — Masquer une vue dans une forme

Le modificateur `.clipShape()` permet de **découper une vue selon une forme géométrique**. C’est parfait pour :
- Créer des **avatars ronds**
- Appliquer des **effets visuels modernes**
- Ajouter du style à des images, fonds ou boutons

### Exemple : Avatar circulaire

---
code
Image("profil")
    .resizable()
    .scaledToFill()
    .frame(width: 120, height: 120)
    .clipShape(Circle())
code
---

💡 L’image est "coupée" en cercle, même si le fichier est rectangulaire.

### 🖼 *Image suggérée*  
Un avatar dans un cercle parfaitement découpé avec `.clipShape(Circle())`.

---

## 🧩 `.overlay()` — Ajouter une vue par-dessus une autre

Le modificateur `.overlay()` permet de **superposer** une vue au-dessus d’une autre. Tu peux y mettre :
- Une forme (ex. un cercle ou une bordure)
- Du texte
- Une autre vue entièrement custom

### Exemple : Image + contour

---
code
Image("profil")
    .resizable()
    .scaledToFill()
    .frame(width: 120, height: 120)
    .clipShape(Circle())
    .overlay(
        Circle()
            .stroke(Color.white, lineWidth: 4)
    )
code
---

💡 Ici, on combine les deux pour obtenir une **image circulaire avec un contour blanc**.

---

## 🔥 Combo complet : avatar stylisé avec ombre

---
code
Image("profil")
    .resizable()
    .scaledToFill()
    .frame(width: 120, height: 120)
    .clipShape(Circle())
    .overlay(
        Circle().stroke(Color.white, lineWidth: 4)
    )
    .shadow(radius: 10)
code
---

### 🖼 *Image suggérée*  
Un avatar rond avec un **contour blanc** et une **ombre douce**.

---

## 🖼 Ajouter un badge avec `.overlay()`

Tu peux aussi superposer une icône ou un texte par-dessus une vue :

---
code
ZStack(alignment: .topTrailing) {
    Image(systemName: "bell.fill")
        .font(.system(size: 50))
        .padding()

    Circle()
        .fill(Color.red)
        .frame(width: 20, height: 20)
        .overlay(
            Text("1")
                .font(.caption2)
                .foregroundColor(.white)
        )
        .offset(x: 5, y: -5)
}
code
---

💡 C’est parfait pour un **badge de notification**.

### 🖼 *Image suggérée*  
Une icône de cloche avec un petit cercle rouge `"1"` positionné en haut à droite.

---

## 🧠 Astuce : Appliquer `.clipShape()` sur d’autres composants

Tu n’es pas limité aux images ! Tu peux découper :
- des `Text`
- des `Buttons`
- des `VStack`, `ZStack`…

### Exemple : bouton en forme de capsule

---
code
Text("Envoyer")
    .padding()
    .background(Color.blue)
    .foregroundColor(.white)
    .clipShape(Capsule())
code
---

💡 Résultat : un **bouton stylisé** et moderne.

---

## 🧪 Bonus : `.overlay()` dynamique avec `@State`

Ajoute ou retire dynamiquement un overlay en fonction d’un état.

---
```
@State private var isSelected = false

Rectangle()
    .fill(Color.orange)
    .frame(width: 150, height: 80)
    .overlay(
        isSelected ?
        Text("✅")
            .font(.largeTitle)
            .foregroundColor(.white)
        : nil
    )
    .onTapGesture {
        isSelected.toggle()
    }
```
---

💡 Appuyer sur le rectangle affiche ou masque un ✅.

---

## ✅ Conclusion

`.clipShape()` et `.overlay()` sont des modificateurs essentiels pour :
- Créer des interfaces **plus visuelles**
- Améliorer la **lisibilité**
- Rendre ton app **plus professionnelle**

Et ce, en **quelques lignes seulement** ✨

📌 **Prochain article : Structurer son code SwiftUI en composants**
