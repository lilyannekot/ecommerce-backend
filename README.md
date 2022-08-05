# E-commerce Backend

## Project Description

This project entailed creating backend for an [e-commerce website](https://drive.google.com/file/d/1hbDGOQHpLH4LVwJbWAbv3ijbm0IPeXM3/view) that allows a user view all categories, products, and tags at once or by ID, as well as update, create new, and delete in all tables.

## Table of Contents

- [Languages and Technology Used](#languages-and-technology-used)
- [Project Demonstration](#project-demonstration)
- [Code Snippet](#code-snippet)
- [Author Links](#author-links)

## Languages and Technology Used

- JavaScript
- SQL

## Project Demonstration

The following gif demonstrates GET requests for all products, categories, and tags.

![All Get Routes](assets/demos/GET-all.gif)

To view entire product demonstration, click [HERE](https://drive.google.com/file/d/1hbDGOQHpLH4LVwJbWAbv3ijbm0IPeXM3/view).

## Code Snippet

The code below is used to get a specific tag by ID number, displaying the tag name along with all of the product details associated with that tag.

```
router.get("/:id", (req, res) => {
  // Find a single tag by its `id`
  // Be sure to include its associated Product data
  Tag.findOne({
    where: {
      id: req.params.id,
    },
    include: {
      model: Product,
      attributes: ["product_name", "price", "stock", "category_id"],
    },
  })
    .then((tagData) => res.json(tagData))
    .catch((err) => {
      console.log(err);
      res.status(500).json(err);
    });
});
```

## Author Links

- [GitHub](https://github.com/lilyannekot)
- [LinkedIn](https://www.linkedin.com/in/lilykot/)
