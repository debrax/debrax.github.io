---
layout: post
title: "Un peu de LINQ"
date: 2021-03-04 20:29:33 +0100
categories: programming
---

Tout développeur C# qui se respecte se doit de connaître LINQ. Le langage de requêtage intégré est souvent utilisé avec Entity Framework pour requêter en base de données, mais il permet également de manipuler efficacement des collections d'objets et même de traiter du XML !

Cet article propose une introduction à "LINQ to Objects", l'utilisation de LINQ avec des collections IEnumerable.

bool: All, Any  
int: Count, Sum, Average, Max, Min  
list: Where, Distinct, OrderBy, OrderByDescending  
transfo: ToList, ToDictionary, GroupBy
2 lists: Intersect, Except, Join, Union

### Filtrage selon condition

```
// Sans LINQ
var discountedProducts = new List<Product>();
foreach (var product in products)
{
    if (product.IsDiscounted)
        discountedProducts.Add(product);
}

// Avec LINQ
var discountedProducts = products
    .Where(p => p.IsDiscounted)
    .ToList();
```

- `Where` : filtre la collection selon un prédicat
- `p => p.IsDiscounted` : lambda de la condition de filtrage (`p` est le produit évalué)
- `ToList` : crée une liste à partir de la collection enumérable

La seule difficulté ici est la notion de lambda qui permet de déclarer facilement le prédicat suivant :

```
Func<Product, bool> IsDiscounted = (p) => p.IsDiscounted;
var discountedProducts = products.Where(IsDiscounted).ToList();
```

Si cela peut vous aider, le concept est proche des fonctions anonymes en Javascript.

### Comptage selon condition

```
// Sans LINQ
var discountedCount = 0;
foreach (var product in products)
{
    if (product.IsDiscounted)
        discountedCount++;
}

// Avec LINQ
var discountedCount = products.Count(p => p.IsDiscounted);
```

Même idée que pour le filtrage ici, la lambda exprime le prédicat de la condition.

### Au moins un élément selon condition

```
// Sans LINQ
var hasDiscountedProduct = false;
foreach (var product in products)
{
    if (product.IsDiscounted)
    {
        hasDiscountedProduct = true;
        break;
    }
}

// Avec LINQ
var hasDiscountedProduct = products.Any(p => p.IsDiscounted);
```

### Au moins un élément

```
// Sans LINQ
var hasAnyProduct = products.Count() > 0;

// Avec LINQ
var hasAnyProduct = products.Any();
```

On remarquera l'expressivité LINQ plus proche du langage métier.

### Tous les éléments selon condition

```
// Sans LINQ
var allDiscountedProducts = true;
foreach (var product in products)
{
    if (!product.IsDiscounted)
    {
        allDiscountedProducts = false;
        break;
    }
}

// Avec LINQ
var allDiscountedProducts = products.All(p => p.IsDiscounted);
```

### Projection en un nouveau type

```
// Sans LINQ
var productModels = new List<ProductModel>();
foreach (var product in products)
{
    var productModel = new ProductModel(product);
    productModels.Add(productModel);
}

// Avec LINQ
var productModels = products
    .Select(p => new ProductModel(p))
    .ToList();
```

### 