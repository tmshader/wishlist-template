---
layout: default
title: My Christmas Wishlist
lang: en
button_text: View
alt_text: "Image for "

wishlist:
  - title: Blue Chocolate
    price: 1
    price_text: $1
    description: Blue as the sky
    tags: [round, chocolate]
    link: https://en.wikipedia.org/wiki/Blue
    image: assets/images/blue.png
    favourite: true

  - title: Red Chocolate
    price: 10
    price_text: $10
    description: Red as a strawberry
    tags: [square, chocolate]
    link: https://en.wikipedia.org/wiki/Red
    image: assets/images/red.png
    favourite: true

  - title: Orange Chocolate
    price: 5
    price_text: $5
    description: Wait... that's not chocolate!
    tags: [round, chocolate]
    link: https://en.wikipedia.org/wiki/Orange
    image: assets/images/orange.png
    favourite: false

  - title: Green Chocolate
    price: 100
    price_text: $100
    description: Green as the grass
    tags: [square, chocolate]
    link: https://en.wikipedia.org/wiki/Green
    image: assets/images/green.png
    favourite: false

categories:
  - name: "My favourites"
    type: "favourite"
    id: my-favourites

  - name: "$1"
    over: 0
    under: 2
    type: "price"
    id: exactly-1

  - name: "Under $10"
    over: 2
    under: 10
    type: "price"
    id: under-10

  - name: "Under $200"
    over: 10
    under: 200
    type: "price"
    id: under-200

  - name: "Chocolates"
    tag: "chocolate"
    type: "tag"
    id: chocolates

  - name: "Round Chocolates"
    tag: "round"
    type: "tag"
    id: round-chocolates

  - name: "Square Chocolates"
    tag: "square"
    type: "tag"
    id: Square-chocolates

category_headers:
  favourite:
    id: favourites
    header: Favourites
    filter: "wish.favourite == true"
  price:
    id: grouped-by-price
    header: Grouped by price
    filter: "wish.price < category.under and wish.price >= category.over"
  tag:
    id: grouped-by-category
    header: Grouped by category
    filter: "wish.tags contains category.tag"

---

{% include content.md %}