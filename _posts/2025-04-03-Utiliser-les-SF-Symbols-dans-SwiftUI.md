---
title: Utiliser les SF Symbols dans SwiftUI
date: 2025-04-03 20:30:00 +0100
categories:
  - SwiftUI
  - Développement iOS
tags:
  - swiftui
  - sfsymbols
  - icônes
  - design
  - apple
description: Apprenez à intégrer les icônes SF Symbols dans vos interfaces SwiftUI, et boostez votre design en quelques lignes de code.
---

# Utiliser les SF Symbols dans SwiftUI

SwiftUI intègre **SF Symbols**, une collection d’icônes vectorielles fournies par Apple, parfaitement adaptées à l’univers iOS, macOS, watchOS et tvOS. Ces icônes sont **scalables, personnalisables** et **s’intègrent nativement** dans vos vues.

Dans cet article, tu vas apprendre à :
- Utiliser une icône avec `Image(systemName:)`
- Personnaliser la taille, la couleur et le style
- Combiner icône et texte avec `Label`
- Naviguer rapidement dans la bibliothèque d’icônes depuis Xcode

---

## 🧱 Ajouter une icône SF Symbol

La base : utiliser le nom du symbole dans `Image(systemName:)`

---
```
Image(systemName: "star.fill")
    .foregroundColor(.yellow)
    .font(.largeTitle)
```
---

💡 **`"star.fill"`** est le nom du symbole. Il existe des centaines d’autres.

---

## 🔎 Accéder rapidement à la bibliothèque SF Symbols dans Xcode

Dans **Xcode**, lorsque tu es dans l’éditeur de code :
- Tape `Image(systemName: "")`
- Clique à l’intérieur des guillemets `""`
- Puis **⇧ Shift + ⌘ Command + L** (le raccourci magique !)

🪄 Cela ouvre la **library contextuelle**, avec **toutes les icônes disponibles** (tu peux chercher `"heart"`, `"arrow"`, `"trash"`, etc.).

![](../assets/images/2025-04-03-Utiliser-les-SF-Symbols-dans-SwiftUI/Xcodeshortcutforsfsymbols.gif)

---

## 🎨 Personnaliser une icône

Tu peux styliser une icône comme n’importe quel texte SwiftUI :

---
```
Image(systemName: "bell.badge.fill")
    .font(.system(size: 40))
    .foregroundColor(.red)
```
---

- `.font()` permet de changer la taille
- `.foregroundColor()` pour la couleur
- Tu peux aussi utiliser `.symbolRenderingMode(.hierarchical)` ou `.palette` pour les styles avancés


---

## 🏷 Combiner texte + icône avec `Label`

---
```
Label("Favori", systemImage: "star.fill")
    .padding()
    .background(Color.yellow.opacity(0.2))
    .cornerRadius(8)
```
---

💡 `Label` aligne automatiquement l’icône et le texte avec les bons espacements.

---

## 🧠 Astuce : Utiliser SF Symbols dans un bouton

---
```
Button(action: {
    print("Partagé !")
}) {
    Image(systemName: "square.and.arrow.up")
        .font(.title2)
}
```
---

💡 Idéal pour des actions comme partage, suppression, navigation…

---

## ⚠️ Compatibilité

- Les SF Symbols sont disponibles à partir de **iOS 13** (certains nécessitent iOS 15+).
- Assure-toi que l’icône choisie est compatible avec la version ciblée.

👉 [Consulte la documentation officielle ici](https://developer.apple.com/sf-symbols/)

---

## ✅ Conclusion

Les **SF Symbols** sont un atout majeur dans SwiftUI :
- Faciles à intégrer
- Personnalisables
- Alignés avec l’écosystème Apple

Et avec le raccourci **⇧⌘L**, tu peux **insérer des icônes en un éclair** directement depuis Xcode !

📌 **Prochain article : Customisation avec `.clipShape()` et `.overlay()` dans SwiftUI !**
