# Automated Reproduction of Placeholder Thumbnail Rendering Bug

## Summary

This test automates the reproduction of a visual UI issue found during exploratory testing on a real estate website.

The bug occurs in the "Últimas Propiedades" sidebar section, where the first property thumbnail fails to load correctly and displays a placeholder image instead of the expected property image.

Unlike common automation scenarios such as forms or login validations, this case focuses on detecting a subtle visual/content rendering issue through DOM and attribute validation.

---

## Objective

Validate that the first property thumbnail in the related properties sidebar loads a placeholder image instead of a valid property thumbnail.

The automation reproduces and confirms the issue consistently.

---

## Environment

* Website: https://www.rcaffaratti.com/
* Browser: Google Chrome
* Framework: Cypress
* OS: Windows 10
* Resolution: 1366x768

---

## Automation Flow

1. Open website homepage
2. Scroll to property listings
3. Open the first available property
4. Locate the "Últimas Propiedades" sidebar widget
5. Select the first thumbnail image
6. Validate that the image source contains a placeholder URL

---

## Validation Logic

The automation does not rely on simple visibility checks.

Instead, it validates the actual image source rendered in the DOM:

```js
.should('have.attr', 'src')
.and('include', 'placehold.it')
```

This confirms that the application is rendering a fallback placeholder image instead of a valid property thumbnail.

---

## Expected Result

The first thumbnail should display a valid property image.

---

## Actual Result

The first thumbnail displays a placeholder image:

```text
https://placehold.it/150x110&text=Inmobiliaria+Caffaratti
```

---

## Severity

Low - Visual/UI Rendering Issue

---

### Automation Reproduction GIF

![Automation Reproduction](./evidence/evidence.gif)

---

## Notes

This bug is interesting from an automation perspective because the issue is not caused by a missing element or failed visibility state.

The image element exists correctly in the DOM, but the rendered source falls back to a placeholder image, making the issue more subtle and requiring attribute-level validation rather than basic UI assertions.

This type of issue is closer to real-world UI validation scenarios commonly encountered in production environments.
