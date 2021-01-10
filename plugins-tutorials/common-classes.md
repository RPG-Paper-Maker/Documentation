---
description: How are used the Common classes in Common folder.
---

# Common classes

## Constants

This countains only static properties. It's used to get very general constants.

## Enum

This contains every Enumeration classes.

## Interpreter

The interpreter used to evaluate formulas. This only contains the `evaluate` method.

## IO

This contains every methods linked to file readding/writting.

## KeyEvent

This class is used to replace the Web KeyEvent class. We can use it to convert Qt keys \(Qt is the framework used for RPG Paper Maker engine\) to JavaScript keys.

## Mathf

This contains every methods related to math calculation.

## Paths

This contains every paths values and especially JSON files paths.

## Platform

This class is specific to the platform \(desktop, web, android, iOS\). This contains properties and methods very specific to the platform you are currently using.

## ScreenResolution

By default, the screen resolution is `640x480`. So when the screen resolution is different, we need to recalculate the elements size. For that we are mainly using `getScreenX` and `getScreenY`.

## Utils

This contains a lot of general utilities methods.

