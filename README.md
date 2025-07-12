# Custom Cache - C# Caching Library 🚀

<image-card alt=".NET" src="https://img.shields.io/badge/.NET-4.7.2%2B%20%7C%20Core%203.1%2B-blueviolet" ></image-card>
<image-card alt="License" src="https://img.shields.io/badge/license-MIT-green" ></image-card>
<image-card alt="Build Status" src="https://img.shields.io/badge/build-passing-brightgreen" ></image-card>

A high-performance, generic caching library for C# applications, providing in-memory caching for any data type with any key type. This library significantly boosts application performance by reducing redundant data fetching operations. ⚡

## Table of Contents
- [Overview](#overview)
- [Problem Statement](#problem-statement)
- [Solution](#solution)
- [Key Features](#key-features)
- [Usage Example](#usage-example)
- [Benefits](#benefits)
- [Use Cases](#use-cases)
- [Requirements](#requirements)
- [Installation](#installation)
- [Contributing](#contributing)
- [License](#license)
- [Support](#support)

## Overview 📋
Custom Cache is a lightweight, thread-safe caching library designed to store frequently accessed data in memory, minimizing costly operations like database queries, API calls, or file system access. It supports generic types for keys and values, making it highly flexible and type-safe.

## Problem Statement 🐌
Applications often face performance bottlenecks when repeatedly fetching the same data from slow sources (e.g., databases, APIs, file systems). For instance, a `DownloadData` method taking 1 second per call can lead to significant delays and resource waste when called multiple times for the same data.

## Solution 💡
The Custom Cache library addresses this by:
- 💾 Storing data in memory for quick access
- 🔧 Supporting any key-value type combination
- ⚡ Reducing data access time for cached items
- 🛡️ Ensuring thread safety for concurrent operations

## Key Features ✨
- **Generic Type Support**: Works with any key type (e.g., `string`, `int`, `Guid`, custom objects) and any data type (e.g., primitives, objects, collections). ✅
- **Performance Optimization**: 
  - First access: Fetches from the source (normal speed). 🐌
  - Subsequent access: Near-instantaneous retrieval from cache. 🏎️
- **Thread Safety**: Safe for multi-threaded applications with concurrent read/write support. 🔒
- **Easy Integration**: Intuitive API with minimal setup. 🔄
- **Design Patterns**:
  - 🎯 **Decorator Pattern**: Enhances data access with caching.
  - 🔗 **Chain of Responsibility**: Handles cache misses gracefully.
  - 📦 **Dictionary**: Uses `Dictionary<TKey, TValue>` for high-performance storage.

installation 🚀

Clone the repository:
```bash  
git clone https://github.com/username/custom-cache.git
```
## Usage Example 💻
Below is an example of how to use the Custom Cache library:

```csharp
using CustomCache;
// Simulated slow data source
private UserData DownloadUserData(string userId)
{
    Thread.Sleep(1000); // Simulate 1-second delay
    return new UserData { Id = userId, Name = "John Doe" };
}
// Usage
var cache = new Cache<string, UserData>();
// First access: Fetches from source (slow)
var userData1 = cache.Get("user123", () => DownloadUserData("user123"));
Console.WriteLine(userData1.Name); // Output: John Doe
// Second access: Served from cache (fast)
var userData2 = cache.Get("user123", () => DownloadUserData("user123"));
Console.WriteLine(userData2.Name); // 
Output: John Doe (instantaneous)
```
Optional Performance Chart
To highlight the performance benefits, here’s a sample chart comparing cached vs. non-cached access times:
<img width="751" height="433" alt="chart" src="https://github.com/user-attachments/assets/901a8332-3dcc-4be2-8b24-72e5be627037" />

Support 📧
For questions or support, please:
Open an issue on GitHub.
Contact us via marwanfarook99@gmail.com

