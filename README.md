# QA Automation - Cypress (Slider Bug Reproduction)

End-to-end automation project using Cypress to reproduce a UI issue found in a real estate website.

## Overview

This project contains an automated test that reproduces a visual and interaction bug found in the property image slider. The issue appears when rapidly interacting with the "next" button in the image gallery, causing the thumbnail section to become unstable or temporarily lose images.

## Tested Application

https://www.dilletpropiedades.com.ar/

## Bug Description

The thumbnail gallery in the property detail page becomes unstable after rapid interaction with the image navigation controls. Observed behavior includes thumbnails shifting incorrectly, temporary disappearance of images, and layout instability in the slider container.

## Test Scenario

The automated test covers the following flow: navigate to homepage, open "Propiedades" section, select the first available property, access image gallery, perform rapid clicks on the "next" button, and validate thumbnail container stability.

## Tech Stack

Cypress, JavaScript, Node.js

## Test File

cypress/e2e/slider-bug.cy.js

## Execution

npm install  
npx cypress open  
npx cypress run  

## Evidence

The automated reproduction of the issue is included in this repository: slider-bug.mp4
