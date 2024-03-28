---
layout: simple
title: Automatisches Deployment eingerichtet
subtitle: zumindest für CDA Orga und Artefacts intern
---
Ich habe heute automatische Deployments eingebaut und zwar für …

### Artefacts (nur intern)

Bislang ist nur ein [automatisches Deployment für den internen Bereich](https://github.com/lucascranach/cranach-artefacts/actions) eingerichtet. Dieses wird gestartet, wenn ein commit auf den [Branch intern](https://github.com/lucascranach/cranach-artefacts/tree/intern) gemacht wird. Das Deployment geht dann in den [internen Bereich](http://lucascranach.org/intern/).

Dabei habe ich diese hübsche Anleitung genutzt [Deploying to a server via SSH and Rsync in a Github Action](https://zellwk.com/blog/github-actions-deploy/).

### CDA Orga

Hier wird jetzt beim Commit auf den Master Branch automatisch deployt auf [den internen Bereich](https://lucascranach.org/intern/blog/). Hierfür habe ich einen neuen Subfolder `blog` angelegt, damit das kein Stress mit den Rechten gibt.
