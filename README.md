# Carbon: A Simple PHP API Extension for DateTime

This presentation will introduce **Carbon**, a powerful PHP library that makes working with dates and times easier and more intuitive. We'll explore its features through interactive examples that you can try out during the session.

---

## Table of Contents
1. [Introduction](#introduction)
2. [Installation and Basic Usage](#installation-and-basic-usage)
3. [Common Operations](#common-operations)
4. [Immutability](#immutability)
5. [Examples and Use Cases](#examples-and-use-cases)
6. [Conclusion](#conclusion)

---

## Introduction

### The Problem with Native PHP Dates
Working with native PHP `DateTime` can be cumbersome and verbose. Carbon simplifies this by providing a clean, fluent API.

### Introducing Carbon
Carbon extends PHP's `DateTime` class, making date and time manipulation easier and more readable.

### Benefits of Using Carbon
- **Readable syntax**: Methods like `addDays()` and `diffForHumans()` are intuitive.
- **Timezone support**: Easily handle timezones.
- **Immutability**: Prevents accidental changes to dates.

---

## Installation and Basic Usage

### Installation (Composer)
To install Carbon, run the following command in your terminal:

```bash
composer require nesbot/carbon
```

### Basic Creation

#### `Carbon::now()`
Get the current date and time.

```php
<?php
require 'vendor/autoload.php';
use Carbon\Carbon;

$now = Carbon::now();
echo "Current time: " . $now;
?>
```

#### `Carbon::today()`
Get the start of today.

```php
$today = Carbon::today();
echo "<br>Start of today: " . $today;
```

#### `Carbon::tomorrow()` and `Carbon::yesterday()`
Get tomorrow's and yesterday's dates.

```php
$tomorrow = Carbon::tomorrow();
echo "<br>Tomorrow: " . $tomorrow;

$yesterday = Carbon::yesterday();
echo "<br>Yesterday: " . $yesterday;
```

#### `Carbon::create()`
Create a specific date and time.

```php
$nextClass = Carbon::create(2025, 1, 9, 10, 0, 0);
echo "<br>Next class: " . $nextClass;
```

#### `Carbon::parse()`
Create a date from a string.

```php
$parsedDate = Carbon::parse('2025-01-15 14:30:00');
echo "<br>Parsed date: " . $parsedDate;
```

---

## Common Operations

### Formatting Dates and Times

#### `format()`
Format dates as desired.

```php
echo "<br>Formatted class date: " . $nextClass->format('l, F jS, Y - g:i A');
```

#### Predefined Formats
Use predefined formatting methods.

```php
echo "<br>Date Time String: " . $nextClass->toDateTimeString();
echo "<br>Date String: " . $nextClass->toDateString();
echo "<br>Formatted Date String: " . $nextClass->toFormattedDateString();
```

### Adding and Subtracting Time

#### `addDays()`, `subDays()`, etc.
Add or subtract time from a date.

```php
$nextClassPlusOneWeek = $nextClass->addDays(7);
echo "<br>Next class (plus 1 week): " . $nextClassPlusOneWeek;

$previousClass = $nextClass->subDays(2);
echo "<br>Previous class: " . $previousClass;
```

#### `addWeekdays()`
Add working days to a date.

```php
$after5Workdays = $now->addWeekdays(5);
echo "<br>After 5 working days: " . $after5Workdays;
```

### Difference Between Dates

#### `diffInDays()`
Calculate the difference between two dates.

```php
$daysUntilClass = $previousClass->diffInDays($nextClass);
echo "<br>Days until next class: " . $daysUntilClass;
```

#### `diffForHumans()`
Get a human-readable difference.

```php
echo "<br>Time until next class in human-readable format: " . $now->diffForHumans($nextClass);
```

### Comparison Operators

#### `isFuture()`, `isPast()`
Check if a date is in the future or past.

```php
if ($nextClass->isFuture()) {
    echo "<br>Next class is in the future!";
}
```

#### `gt()`, `lt()`
Compare dates using greater-than or less-than.

```php
if ($previousClass->lt($nextClass)) {
    echo "<br>Our previous class was before our next class";
}
```

### Timezones

#### `setTimezone()`
Work with different timezones.

```php
$nowInLondon = Carbon::now('Europe/London');
echo "<br>Current Time in London: " . $nowInLondon;
echo "<br>Timezone: " . $nowInLondon->timezone;
```

---

## Immutability

### Demonstrate Immutability
Carbon uses immutability to prevent accidental changes to dates.

```php
$originalDate = Carbon::now();
$modifiedDate = $originalDate->addDays(5);
echo "<br>Original Date: " . $originalDate;
echo "<br>Modified Date: " . $modifiedDate;

if ($originalDate->diffInDays($modifiedDate) == 5) {
    echo "<br>Date not modified!";
}
```

---

## Examples and Use Cases

- **Calculate age from a birthdate**.
- **Generate a list of upcoming events**.
- **Countdown to a specific date**.

---

## Conclusion

### Recap Benefits
- Simplified date and time manipulation.
- Fluent and readable syntax.
- Timezone support and immutability.

### Further Learning
- [Carbon Documentation](https://carbon.nesbot.com/docs/)
- Explore more advanced features like localization and macros.

---

By following this guide and trying out the examples, you'll quickly see how Carbon can make working with dates and times in PHP a breeze!
```

### Key Features of This README.md
1. **Clear Structure**: Sections are well-organized with headings and subheadings.
2. **Interactive Examples**: Code snippets are provided for each concept, making it easy to follow along.
3. **Real-World Context**: Examples are relatable and practical.
4. **Markdown Formatting**: Easy to read and share, with syntax highlighting for code blocks.
