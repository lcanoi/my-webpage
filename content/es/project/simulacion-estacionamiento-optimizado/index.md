---
title: MySpot - Simulación Estacionamiento Optimizado
subtitle: ""
date: 2021-09-01T03:57:45.024Z
summary: Simulación de multiagentes con un sistema inteligente para mejorar el tiempo de espera de carros al buscar un lugar de estacionamiento en una plaza. Hecho en Unity
draft: false
featured: false
tags:
  - 1
  - 2
  - 4
  - C#
  - Unity
external_link: ""
image:
  filename: featured.png
  focal_point: Smart
  preview_only: false
---

## Resumen
MySpot es el resultado de la solución creada para un reto de Modelación de sistemas multiagentes con gráficas computacionales. Este brinda una simulación de multiagentes en el cual un sistema inteligente ayuda a mejorar el tiempo de espera al momento de buscar un cajón de estacionamiento en una plaza.

## Ejemplo de la Simulación:
[![Simulación](https://img.youtube.com/vi/YWoAGjl28zU/0.jpg)](https://www.youtube.com/watch?v=YWoAGjl28zU)

## Encuentra el projecto en Github
[**MySpot**](https://github.com/lcanoi/OptimizedParkingSimulation)

## Herramientas
Para la creación de este proyecto, las herramientas que se usaron principalmente fueron:
+ NetLogo: para la simulación inicial y prueba de algoritmos (área de multiagentes). 
+ Unity: para el desarrollo del proyecto final (área de multiagentes y Gráficas).

## Mejoras por realizar
+ Mejorar la inteligencia del sistema de sensores en el estacionamiento:
  + No solo asignar lugares de estacionamiento a los autos cerca de la tienda a la que quieren ir, sino también considerar el tiempo que cada uno tardará aproximadamente en la tienda. Puede que sea mejor aparcar a los coches que permanezcan durante mucho tiempo más alejados y, al mismo tiempo, dar prioridad a los lugares más cercanos para los coches que se van rápidamente.
  + También debe considerar de guardar suficientes lugares de estacionamiento para discapacitados cerca de cada tienda.
+ Añadir coches a la circulación que no vayan a ninguna tienda, solo que pasen por la calle.
+ Corregir errores/bugs que pueden ocurrir al ejecutar una simulación con una tasa de generación de automóviles rápida y una alta concentración de automóviles.
