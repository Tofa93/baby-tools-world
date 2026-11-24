---
toc_max_heading_level: 4
sidebar_position: 2
tags:
  - project
  - checklist
sidebar_label: Checklist
description: An editable, copyable checklist with all tasks for the Baby Tools World project.
---

# Baby Tools World - Checklist

This checklist contains the most important project requirements. They are split into several categories to make it easier for you to get started.

When you submit your project, send us the credentials of your superuser so that we can log in and look around your Baby Tools World.
Send the credentials as a **comment with your submission** on the Campus. Do **not** store them in the repository.

For code projects, always proceed as follows:

1. Fork our repository into your GitHub namespace.
2. Remove the fork relationship of your repository.
3. Create a feature branch `add-product-tags` for the implementation in your repository.
4. Do all development work on your feature branch. Create a **pull request** for the feature branch that you can send us for a code review. Keep the feature branch until the mentors approve the project and the feature branch for merging.

## 1. Repository

### .gitignore

- [ ] The `.gitignore` file ignores all file patterns that are usually ignored in Python projects.
- [ ] The `.gitignore` file also ignores the virtual environment.
- [ ] The `.gitignore` file also ignores environment variable files (`.env` files), no matter whether they are named `.env`, `local.env`, `development.env`, or similar.
  - [ ] The only exception to this rule is the file `example.env`.

### README.md

- [ ] The README starts with an H1 heading containing the repository or project name.
- [ ] Right at the beginning, the README contains a description of the repository that is not too technical. The description has no more than 2-5 sentences.
- [ ] A "Quickstart" section is part of the README. It briefly lists the prerequisites and describes how to get started quickly.
- [ ] A "Usage" section describes advanced usage and the configuration of the application.

### Django code

- [x] `products/models.py`:
  - [x] Extend `models.py` with a model named `Tag` that has the following attributes:
    - [x] `name`
    - [x] `id` (assigned automatically by Django)
    - [x] `created_at` (generated automatically) - **this attribute is read-only**
    - [x] `updated_at` (generated automatically) - **this attribute is read-only**
  - [x] Extend the `Product` model with a new attribute `tags`. It has a many-to-many relationship to the tags via their ID.
    - [x] Tags can be unset or empty on a product, which means tags are not required for products.
- [x] `products/templates/product.html` (Django Template Language):
  - [x] Extend `product.html` so that the product tags are rendered below the rating summary.
    - [x] On the product details page, show the tags linked to a product at the bottom of the product card, above the "Buy" button.
    - [x] Show a heading with the label "Product-Tags" above the tags.
    - [x] If a product has **no** tags, show the heading and the label "no tags available" below it.
- [x] `products/admin.py`:
  - [x] Extend the admin so that the `Tag` model is visible in the Django admin and new `Tag` objects can be created and managed in the admin panel.
    - [x] Import the `Tag` model class.
    - [x] Register the `Tag` model.
    - [x] Extend `ProductAdmin` with a filter.
- [x] `products/views.py`:
  - [x] Extend `views.py` so that the following applies:
    - [x] After a review is submitted successfully, all form fields (rating stars and comment text) are cleared.

### requirements.txt

- [ ] All package dependencies are listed in `requirements.txt`.
- [ ] `requirements.txt` contains only packages with a pinned version.

## 2. Code style

- [ ] Your Python code follows PEP 8 as its code style standard. You can use a linting tool such as flake8 for this. More information:
  - [ ] [PEP 8 Style Guide for Python](https://peps.python.org/pep-0008/)
  - [ ] [Flake8 documentation](https://flake8.pycqa.org/en/latest/)
- [ ] Follow these naming conventions:
  - [ ] Class names -> PascalCase
  - [ ] Variables -> snake_case
- [ ] Your Python functions use type hints for parameters, return values, and variables.
- [ ] Every function in your Python code has a docstring that describes what the function does, which parameters it accepts, and which return value to expect.

## 3. Documentation

This section describes what we expect from the documentation of your project. The following items help you not to forget anything.

- [ ] The language of the documentation (README and code comments) is **English**.
- [ ] The documentation is written in complete sentences, for example in the README file of a repository.
  - [ ] For longer documentation, create a separate `docs` folder in the repository that contains the documentation.

## 4. Hints

### General hints

- [ ] Set up and run your project in a virtual environment.
- [ ] If you have questions or something is unclear, contact us via the ticket system.
- [ ] You can use the official Django and Python documentation at any time. If you have questions about the documentation, send us a link to the relevant page.
  - [ ] [Django documentation](https://docs.djangoproject.com/en/5.2/)
  - [ ] [Python documentation](https://docs.python.org/3/)
- [ ] Before you submit, start your application at least once on your own computer and test everything.
- [ ] In addition to your GitHub repository, record and share a short Loom video (max. 5 minutes) in which you show your submission and present what you did. You do not have to mention every detail, but briefly explain and show all relevant steps.
- [ ] The migrations for your changes are created and applied.

## 5. Testing

Before you submit the project, make sure that you have tested the following:

- [ ] Baby Tools World is reachable at `<YOUR_VM_IP>:8000`.
- [ ] The application shows products and categories.
  - [ ] On a product page, you can see more information about a product and its tags.
- [ ] You can create new products, categories, and tags in the admin panel.
- [ ] The comment field is cleared after submitting.
- [ ] You can build your container image with the command from the README.
- [ ] You can start the container by following the README and reach the application in the browser again.