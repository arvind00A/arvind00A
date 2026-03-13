<div align="center">

# 🚀 C# Learning Journey

### Day-by-Day Revision & Notes
> A structured, beginner-to-proficient C# tutorial series with definitions, syntax, examples, and best practices.

[![C#](https://img.shields.io/badge/C%23-239120?style=for-the-badge&logo=c-sharp&logoColor=white)](https://docs.microsoft.com/en-us/dotnet/csharp/)
[![.NET](https://img.shields.io/badge/.NET-5C2D91?style=for-the-badge&logo=.net&logoColor=white)](https://dotnet.microsoft.com/)
[![Visual Studio](https://img.shields.io/badge/Visual%20Studio-2026-5C2D91?style=for-the-badge&logo=visual-studio&logoColor=white)](https://visualstudio.microsoft.com/)
[![Status](https://img.shields.io/badge/Status-Active-brightgreen?style=for-the-badge)](https://github.com/arvind01A)
[![Days](https://img.shields.io/badge/Days%20Completed-9-blue?style=for-the-badge)](https://github.com/arvind01A)

<br/>

**Author:** Arvind Kumar &nbsp;|&nbsp; **GitHub:** [@arvind01A](https://github.com/arvind01A) &nbsp;|&nbsp; **Started:** March 2026

</div>

---

## 📖 Overview

This repository documents my daily C# revision — from basics to advanced concepts.
Each day includes:

| 📌 What's Inside | Description |
|---|---|
| 📝 **Definitions** | Clear, concise explanations |
| 💻 **Syntax Examples** | Ready-to-reference patterns |
| 📋 **Code Snippets** | Copy-paste ready code |
| ⚠️ **Pitfalls** | Key differences & common mistakes |
| 📊 **Summary Tables** | Quick-reference comparisons |

> 💡 Perfect for **beginners**, **self-learners**, or anyone **refreshing C# skills** in 2026!

---

## 🎯 Goal

```
Fundamentals → OOP → Collections → Exception Handling → File I/O → Expert_level-1 → Expert_level-2 → Expert_level-3
```

---

## 📅 Progress & Completed Days

| # | Day | Topic | Subtopics | Status |
|---|-----|-------|-----------|--------|
| 1 | **Day 1** | [Fundamentals](#-day-1--fundamentals) | Variables · Operators · Control Flow · Loops | ✅ Done |
| 2 | **Day 2** | [Classes & Objects](#-day-2--classes--objects) | Methods · Parameters · Constructors · Fields | ✅ Done |
| 3 | **Day 3** | [OOP Pillars](#-day-3--oop-pillars) | Encapsulation · Inheritance · Abstraction · Polymorphism | ✅ Done |
| 4 | **Day 4** | [Data Structures](#-day-4--basic-data-structures) | Arrays · Strings · StringBuilder · Tuples | ✅ Done |
| 5 | **Day 5** | [Generics](#-day-5--generics) | Generic Classes · Methods · Constraints | ✅ Done |
| 6 | **Day 6** | [Collections](#-day-6--collections) | Non-Generic · Generic · Specialized · Concurrent | ✅ Done |
| 7 | **Day 7** | [Exception & File Handling](#-day-7--exception--file-handling) | try-catch-finally · throw vs throw ex · Built-in Exceptions · Global Handler · StreamReader/Writer · File & Dir Operations · Async File I/O | ✅ Done |
| 8 | **Day 8** | [Expert I — Functional Programming & Delegates](#-day-8--expert-i--functional-programming--delegates) | Extension Methods · Lambda · LINQ · Pattern Matching · Pure Functions · Action/Func/Predicate · Anonymous Methods · Events | ✅ Done |
| 9 | **Day 9** | [Expert II — Multithreading, Async & Serialization](#-day-9--expert-ii--multithreading-async--serialization) | Thread Class · Task Class · Parallel.ForEach · Async/Await · Exception in Async · IAsyncEnumerable · Binary/JSON/XML Serialization | ✅ Done |

> 🕒 **Last updated:** March 13, 2026

---

## 📚 Day-by-Day Notes

---

### 🟣 Day 1 — Fundamentals

<details>
<summary><b>Click to expand</b></summary>

#### 📦 Variables & Data Types
```csharp
int age = 25;
double price = 9.99;
string name = "Arvind";
bool isActive = true;
char grade = 'A';
var inferred = 42;          // Type inferred by compiler
const double PI = 3.14159;  // Constant
```

#### ➕ Operators
```csharp
// Arithmetic
int sum = 10 + 5;    // 15
int mod = 10 % 3;    // 1

// Comparison
bool isEqual = (5 == 5);   // true
bool notEqual = (5 != 4);  // true

// Logical
bool result = (true && false);  // false
bool either = (true || false);  // true
```

#### 🔀 Control Statements
```csharp
// if / else if / else
if (age >= 18) { Console.WriteLine("Adult"); }
else if (age >= 13) { Console.WriteLine("Teen"); }
else { Console.WriteLine("Child"); }

// switch expression (C# 8+)
string label = age switch {
    >= 18 => "Adult",
    >= 13 => "Teen",
    _     => "Child"
};
```

#### 🔁 Loops
```csharp
for (int i = 0; i < 5; i++) { /* ... */ }
while (condition) { /* ... */ }
do { /* ... */ } while (condition);
foreach (var item in collection) { /* ... */ }
```

#### ⏭️ Jump Statements
```csharp
break;      // Exit loop
continue;   // Skip to next iteration
return;     // Exit method
goto label; // Jump to label (avoid!)
```

</details>

---

### 🔵 Day 2 — Classes & Objects

<details>
<summary><b>Click to expand</b></summary>

#### 🏗️ Methods & Parameters
```csharp
// Return types
public int Add(int a, int b) => a + b;
public void Print(string msg) => Console.WriteLine(msg);

// Parameter passing
public void Swap(ref int a, ref int b) { (a, b) = (b, a); }
public void TryParse(string s, out int result) { result = int.Parse(s); }

// Optional parameters & named arguments
public void Greet(string name, string greeting = "Hello") =>
    Console.WriteLine($"{greeting}, {name}!");

Greet(name: "Arvind", greeting: "Hi");
```

#### 🏛️ Constructors
```csharp
public class Person
{
    public string Name { get; set; }
    public int Age { get; set; }

    public Person() { }                          // Default
    public Person(string name) => Name = name;   // Parameterized
    public Person(Person other)                  // Copy
        => (Name, Age) = (other.Name, other.Age);

    static Person() { /* Runs once, before first use */ } // Static
}
```

#### 🗂️ Fields
```csharp
public class Circle
{
    private double _radius;          // Private field
    public static int Count = 0;     // Static field
    public readonly double Id;       // Readonly (set in constructor only)
}
```

</details>

---

### 🟢 Day 3 — OOP Pillars

<details>
<summary><b>Click to expand</b></summary>

#### 🔒 Encapsulation
```csharp
public class BankAccount
{
    private decimal _balance;

    public decimal Balance
    {
        get => _balance;
        private set => _balance = value >= 0 ? value : 0;
    }
}
```

**Access Modifiers:**
| Modifier | Accessible From |
|---|---|
| `public` | Anywhere |
| `private` | Same class only |
| `protected` | Same class + subclasses |
| `internal` | Same assembly |
| `protected internal` | Same assembly or subclasses |

#### 🧬 Inheritance
```csharp
public class Animal
{
    public virtual void Speak() => Console.WriteLine("...");
}

public class Dog : Animal
{
    public override void Speak() => Console.WriteLine("Woof!");
    public Dog(string name) : base() { }
}
```

#### 🎭 Abstraction
```csharp
public abstract class Shape
{
    public abstract double Area();
    public void Display() => Console.WriteLine($"Area: {Area()}");
}

public interface IDrawable
{
    void Draw();
    string Color { get; set; }
}
```

#### 🔄 Polymorphism
```csharp
// Compile-time (Method Overloading)
public int Multiply(int a, int b) => a * b;
public double Multiply(double a, double b) => a * b;

// Runtime (Method Overriding)
Animal animal = new Dog();
animal.Speak();  // "Woof!" → resolved at runtime
```

#### 📇 Indexers
```csharp
public class WordCollection
{
    private string[] _words = new string[10];
    public string this[int index]
    {
        get => _words[index];
        set => _words[index] = value;
    }
}
```

</details>

---

### 🟡 Day 4 — Basic Data Structures

<details>
<summary><b>Click to expand</b></summary>

#### 📐 Arrays
```csharp
int[] nums = { 1, 2, 3, 4, 5 };
int[,] matrix = new int[3, 3];
int[][] jagged = new int[3][];
jagged[0] = new int[] { 1, 2, 3 };

Array.Sort(nums);
Array.Reverse(nums);
int idx = Array.IndexOf(nums, 3);
int[] copy = (int[])nums.Clone();
```

#### 🔤 Strings
```csharp
string s = "Hello, Arvind!";
s.ToUpper();   s.Contains("Arvind");   s.Replace("Hello", "Hi");
s.Split(',');  s.Trim();

string msg = $"Name: {name}, Age: {age}";

var sb = new StringBuilder();
sb.Append("Hello");
sb.AppendLine(" World");
string result = sb.ToString();
```

#### 📦 Tuples
```csharp
var person = (Name: "Arvind", Age: 25, City: "Delhi");
Console.WriteLine(person.Name);
var (name, age, city) = person;
```

</details>

---

### 🟠 Day 5 — Generics

<details>
<summary><b>Click to expand</b></summary>

#### 📦 Generic Classes & Methods
```csharp
public class Box<T> { public T Value { get; set; } }
public class Pair<TKey, TValue> { public TKey Key; public TValue Value; }

public static void Swap<T>(ref T a, ref T b) => (a, b) = (b, a);
Swap<int>(ref x, ref y);   // explicit
Swap(ref x, ref y);        // inferred
```

#### 📏 Generic Constraints
| Constraint | Meaning |
|---|---|
| `where T : class` | Reference types only |
| `where T : struct` | Value types only |
| `where T : new()` | Must have parameterless constructor |
| `where T : IComparable<T>` | Must implement IComparable |

</details>

---

### 🔷 Day 6 — Collections

<details>
<summary><b>Click to expand</b></summary>

#### 🗂️ Non-Generic (`System.Collections`) — ⚠️ Avoid
```csharp
ArrayList list = new ArrayList();   // mixed types
Hashtable ht   = new Hashtable();
Queue queue    = new Queue();
Stack stack    = new Stack();
```

#### ✅ Generic (`System.Collections.Generic`)
```csharp
List<int> numbers = new() { 1, 2, 3 };
var scores = new Dictionary<string, int>();
var set    = new HashSet<string>();
var queue  = new Queue<string>();
var stack  = new Stack<int>();
var linked = new LinkedList<int>();
var sorted = new SortedList<string, int>();
```

#### ⚡ Concurrent (`System.Collections.Concurrent`)
```csharp
ConcurrentDictionary<string, int> dict = new();
ConcurrentQueue<string> queue = new();
ConcurrentBag<int> bag = new();
```

**Quick Comparison:**
| Collection | Ordered | Unique | Key-Value | Thread-Safe |
|---|---|---|---|---|
| `List<T>` | ✅ | ❌ | ❌ | ❌ |
| `Dictionary<K,V>` | ❌ | ✅ Keys | ✅ | ❌ |
| `HashSet<T>` | ❌ | ✅ | ❌ | ❌ |
| `SortedList<K,V>` | ✅ | ✅ Keys | ✅ | ❌ |
| `ConcurrentDictionary` | ❌ | ✅ Keys | ✅ | ✅ |

</details>

---

### 🔴 Day 7 — Exception & File Handling

<details>
<summary><b>Click to expand</b></summary>

#### 🔁 try-catch-finally
```csharp
try   { int r = 10 / int.Parse("0"); }
catch (DivideByZeroException ex) { Console.WriteLine(ex.Message); }
catch (FormatException ex)       { Console.WriteLine(ex.Message); }
catch (Exception ex)             { Console.WriteLine(ex.Message); } // last
finally { Console.WriteLine("Always runs — cleanup here!"); }
```

#### 🚀 throw vs throw ex
| | `throw` | `throw ex` |
|---|---|---|
| **Stack trace** | ✅ Preserved | ❌ Reset |
| **Best practice** | ✅ Always prefer | ⚠️ Avoid |

#### 🧱 Built-in Exceptions
| Exception | Thrown When |
|---|---|
| `ArgumentNullException` | Null argument passed |
| `IndexOutOfRangeException` | Invalid array index |
| `NullReferenceException` | Null object access |
| `FormatException` | Invalid string format |
| `DivideByZeroException` | Integer division by zero |
| `FileNotFoundException` | File does not exist |

#### 📁 File Handling (`System.IO`)
```csharp
// Write / Read
using var writer = new StreamWriter("notes.txt");
writer.WriteLine("Hello!");
using var reader = new StreamReader("notes.txt");
string content = reader.ReadToEnd();

// File operations
File.WriteAllText("log.txt", "entry");
File.AppendAllText("log.txt", "\nmore");
File.Copy("a.txt", "b.txt");  File.Delete("old.txt");
string combined = Path.Combine("logs", "app.log");

// Async
string text = await File.ReadAllTextAsync("notes.txt");
await File.WriteAllTextAsync("out.txt", "async write");
```

</details>

---

### 🟤 Day 8 — Expert I: Functional Programming & Delegates

<details>
<summary><b>Click to expand</b></summary>

#### 🔌 Extension Methods
```csharp
public static class StringExtensions
{
    public static string Capitalize(this string s)
        => string.IsNullOrEmpty(s) ? s : char.ToUpper(s[0]) + s[1..];
    public static bool IsEmail(this string s) => s.Contains('@') && s.Contains('.');
}
"hello".Capitalize();   // "Hello"
"a@b.com".IsEmail();    // true
```

#### λ Lambda Expressions
```csharp
Func<int, int>      square  = x => x * x;
Func<int, int, int> add     = (a, b) => a + b;
Action<string>      print   = msg => Console.WriteLine(msg);
Predicate<int>      isEven  = n => n % 2 == 0;

var evens   = numbers.Where(n => n % 2 == 0).ToList();
var doubled = numbers.Select(n => n * 2).ToList();
```

#### 🔍 LINQ
```csharp
// Method syntax (most common)
var result = students
    .Where(s => s.Score >= 80)
    .OrderByDescending(s => s.Score)
    .Select(s => s.Name);

// Key operators
nums.Where(n => n > 5);            // filter
nums.Select(n => n * n);           // project
nums.OrderBy(n => n);              // sort
nums.GroupBy(n => n % 2 == 0);     // group
nums.Take(3);  nums.Skip(7);       // paginate
nums.Sum();  nums.Average();       // aggregate
a.Union(b);  a.Intersect(b);       // set ops
```

#### 🎭 Pattern Matching (C# 8+)
```csharp
string desc = shape switch
{
    Circle c when c.Radius > 10 => "Large circle",
    Circle c                    => "Small circle",
    Rectangle r                 => $"{r.Width}x{r.Height}",
    _                           => "Unknown"
};
```

#### 📣 Delegates — Action, Func & Predicate
```csharp
Action<string>       greet   = name => Console.WriteLine($"Hi {name}!");
Func<int, int>       square  = x => x * x;
Predicate<int>       isEven  = n => n % 2 == 0;

// Multicast
Action log = () => Console.WriteLine("Log 1");
log += () => Console.WriteLine("Log 2");
log();  // prints both
```

#### 📡 Events
```csharp
public class OrderService
{
    public event EventHandler<OrderEventArgs> OrderPlaced;
    public void PlaceOrder(string item) => OrderPlaced?.Invoke(this, new(item));
}

service.OrderPlaced += (s, e) => Console.WriteLine($"Order: {e.Item}");
service.PlaceOrder("Laptop");
```

</details>

---

### ⚡ Day 9 — Expert II: Multithreading, Async & Serialization

<details>
<summary><b>Click to expand</b></summary>

---

## 🧵 Multithreading

#### 🔵 Thread Class
> Low-level OS thread. Use for long-running background work where you need direct thread control.

```csharp
using System.Threading;

// Basic thread creation
Thread t = new Thread(() =>
{
    Console.WriteLine($"Thread {Thread.CurrentThread.ManagedThreadId} running");
    Thread.Sleep(1000);   // simulate work
});
t.Name      = "WorkerThread";
t.IsBackground = true;    // dies when main thread exits
t.Start();
t.Join();                 // wait for thread to finish

// Passing data
Thread t2 = new Thread(obj =>
{
    string msg = (string)obj!;
    Console.WriteLine($"Received: {msg}");
});
t2.Start("Hello from main!");

// Thread synchronization — lock
private static readonly object _lock = new();
private static int _counter = 0;

Thread[] threads = Enumerable.Range(0, 5)
    .Select(_ => new Thread(() =>
    {
        lock (_lock)     // only one thread at a time
        {
            _counter++;
            Console.WriteLine($"Counter: {_counter}");
        }
    })).ToArray();

Array.ForEach(threads, t => t.Start());
Array.ForEach(threads, t => t.Join());
```

> ⚠️ **Prefer `Task` over `Thread`** for most scenarios — Tasks use the thread pool and are much more efficient.

---

#### 🟢 Task Class (TPL — Task Parallel Library)
> Higher-level abstraction over threads. Uses the thread pool automatically.

```csharp
using System.Threading.Tasks;

// Fire and forget
Task.Run(() => Console.WriteLine("Running on thread pool"));

// Returning a value
Task<int> task = Task.Run(() =>
{
    Thread.Sleep(500);
    return 42;
});
int result = await task;   // or task.Result (blocking — avoid!)
Console.WriteLine(result); // 42

// Chaining with ContinueWith
Task.Run(() => "Step 1")
    .ContinueWith(t => $"{t.Result} → Step 2")
    .ContinueWith(t => Console.WriteLine(t.Result));

// Running multiple tasks
Task<int> t1 = Task.Run(() => { Thread.Sleep(200); return 1; });
Task<int> t2 = Task.Run(() => { Thread.Sleep(100); return 2; });
Task<int> t3 = Task.Run(() => { Thread.Sleep(300); return 3; });

// Wait for ALL to finish
int[] results = await Task.WhenAll(t1, t2, t3);  // [1, 2, 3]

// Wait for FIRST to finish
Task<int> first = await Task.WhenAny(t1, t2, t3);
Console.WriteLine(await first);   // 2 (fastest)

// Task cancellation
var cts = new CancellationTokenSource();
cts.CancelAfter(TimeSpan.FromSeconds(3));

Task longTask = Task.Run(async () =>
{
    for (int i = 0; i < 10; i++)
    {
        cts.Token.ThrowIfCancellationRequested();
        await Task.Delay(500);
        Console.WriteLine($"Step {i}");
    }
}, cts.Token);

try   { await longTask; }
catch (OperationCanceledException) { Console.WriteLine("Task cancelled!"); }
```

**Thread vs Task:**
| | `Thread` | `Task` |
|---|---|---|
| **Level** | Low-level OS thread | High-level abstraction |
| **Thread pool** | ❌ Creates new thread | ✅ Reuses pool threads |
| **Return value** | ❌ Not directly | ✅ `Task<T>` |
| **Cancellation** | Manual | ✅ `CancellationToken` |
| **Async/await** | ❌ | ✅ |
| **Use when** | Fine control needed | Most scenarios |

---

#### 🔴 Parallel Programming — `Parallel.ForEach`
> CPU-bound work distributed across multiple cores automatically.

```csharp
using System.Threading.Tasks;

var items = Enumerable.Range(1, 20).ToList();

// Parallel.ForEach — processes items on multiple threads
Parallel.ForEach(items, item =>
{
    Console.WriteLine($"Processing {item} on thread {Thread.CurrentThread.ManagedThreadId}");
});

// With ParallelOptions — limit thread count
Parallel.ForEach(items,
    new ParallelOptions { MaxDegreeOfParallelism = 4 },
    item => ProcessItem(item));

// Parallel.For — indexed version
Parallel.For(0, 10, i =>
{
    Console.WriteLine($"i={i} on thread {Thread.CurrentThread.ManagedThreadId}");
});

// Parallel.Invoke — run multiple actions concurrently
Parallel.Invoke(
    () => Console.WriteLine("Task A"),
    () => Console.WriteLine("Task B"),
    () => Console.WriteLine("Task C")
);

// Thread-safe aggregation with Interlocked
int total = 0;
Parallel.ForEach(items, item =>
{
    Interlocked.Add(ref total, item);  // atomic — no lock needed
});
Console.WriteLine($"Total: {total}");  // 210
```

> ⚠️ **Don't use Parallel for I/O-bound work** (network, file, DB) — use `async/await` instead.
> **Parallel is for CPU-bound** work (calculations, data processing, image processing).

---

## ⚡ Asynchronous Programming

#### 🔵 Async and Await
> Non-blocking execution — the thread is released while waiting, not blocked.

```csharp
// Basic pattern
public async Task<string> FetchDataAsync(string url)
{
    using var client = new HttpClient();
    string data = await client.GetStringAsync(url);  // thread released here
    return data.ToUpper();
}

// void async — only for event handlers
private async void Button_Click(object sender, EventArgs e)
{
    await DoWorkAsync();  // OK in event handler
}

// ✅ Always return Task, not void (except event handlers)
public async Task DoWorkAsync()
{
    await Task.Delay(1000);
    Console.WriteLine("Done!");
}

// Calling async methods
string result = await FetchDataAsync("https://api.example.com");

// ConfigureAwait(false) — avoid deadlocks in library code
public async Task<string> LibraryMethodAsync()
{
    var data = await GetDataAsync().ConfigureAwait(false);
    return Process(data);
}

// Run sync code asynchronously
string result2 = await Task.Run(() => HeavyComputation());

// ValueTask — for frequently called methods that often complete synchronously
public async ValueTask<int> GetCachedValueAsync(int key)
{
    if (_cache.TryGetValue(key, out int val)) return val;  // sync fast path
    return await LoadFromDbAsync(key);                      // async slow path
}
```

---

#### 🔴 Exception Handling in Async Methods

```csharp
// ✅ Standard try-catch works normally with await
public async Task RunAsync()
{
    try
    {
        await Task.Delay(100);
        throw new InvalidOperationException("Async error!");
    }
    catch (InvalidOperationException ex)
    {
        Console.WriteLine($"Caught: {ex.Message}");
    }
    finally
    {
        Console.WriteLine("Cleanup in async finally");
    }
}

// Multiple tasks — AggregateException
Task t1 = Task.Run(() => throw new Exception("Error 1"));
Task t2 = Task.Run(() => throw new Exception("Error 2"));

try
{
    await Task.WhenAll(t1, t2);
}
catch (Exception ex)
{
    // Only first exception surfaced by await
    Console.WriteLine(ex.Message);
}

// ✅ Inspect ALL exceptions from WhenAll
var tasks = new[] { t1, t2 };
await Task.WhenAll(tasks);   // swallow; then check:
foreach (var t in tasks.Where(t => t.IsFaulted))
    Console.WriteLine(t.Exception?.InnerException?.Message);

// ⚠️ Never do async void (exceptions are unobservable)
// ❌ BAD
private async void DoWork() { await Task.Delay(1000); throw new Exception(); }

// ✅ GOOD
private async Task DoWorkAsync() { await Task.Delay(1000); throw new Exception(); }
```

---

#### 🟢 Async Streams — `IAsyncEnumerable<T>`
> Stream data asynchronously — yield items one at a time without loading all into memory.

```csharp
// Producer — async generator
public async IAsyncEnumerable<int> GenerateNumbersAsync(
    int count,
    [EnumeratorCancellation] CancellationToken ct = default)
{
    for (int i = 0; i < count; i++)
    {
        ct.ThrowIfCancellationRequested();
        await Task.Delay(100, ct);     // simulate async fetch
        yield return i;                // yield one item at a time
    }
}

// Consumer — await foreach
await foreach (int num in GenerateNumbersAsync(10))
{
    Console.WriteLine($"Received: {num}");
}

// Real-world: stream DB rows, API pages, file lines
public async IAsyncEnumerable<Order> StreamOrdersAsync()
{
    await using var conn = new SqlConnection(connStr);
    await conn.OpenAsync();
    var cmd = new SqlCommand("SELECT * FROM Orders", conn);
    await using var reader = await cmd.ExecuteReaderAsync();
    while (await reader.ReadAsync())
        yield return MapOrder(reader);
}
```

**`IEnumerable<T>` vs `IAsyncEnumerable<T>`:**
| | `IEnumerable<T>` | `IAsyncEnumerable<T>` |
|---|---|---|
| **Iteration** | `foreach` | `await foreach` |
| **Blocking** | ✅ Blocks thread | ❌ Non-blocking |
| **Use for** | In-memory data | DB, API, file streams |
| **Requires** | - | `async` / `yield return` |

---

## 💾 Serialization

#### 🟢 JSON Serialization (`System.Text.Json`)

```csharp
using System.Text.Json;
using System.Text.Json.Serialization;

public class Person
{
    public string Name { get; set; }
    public int Age { get; set; }

    [JsonPropertyName("email_address")]    // custom JSON key
    public string Email { get; set; }

    [JsonIgnore]                           // exclude from JSON
    public string Password { get; set; }
}

var person = new Person { Name = "Arvind", Age = 25, Email = "a@b.com" };

// Serialize → JSON string
var options = new JsonSerializerOptions { WriteIndented = true };
string json = JsonSerializer.Serialize(person, options);
// {
//   "Name": "Arvind",
//   "Age": 25,
//   "email_address": "a@b.com"
// }

// Deserialize → object
Person? p2 = JsonSerializer.Deserialize<Person>(json);
Console.WriteLine(p2?.Name);   // "Arvind"

// Serialize collection
var people = new List<Person> { person };
string jsonList = JsonSerializer.Serialize(people);

// Async serialize to stream (large data)
await using var stream = File.OpenWrite("data.json");
await JsonSerializer.SerializeAsync(stream, person);
```

---

#### 🔵 XML Serialization (`System.Xml.Serialization`)

```csharp
using System.Xml.Serialization;

[XmlRoot("Person")]
public class Person
{
    [XmlElement("FullName")]
    public string Name { get; set; }

    [XmlAttribute("age")]
    public int Age { get; set; }

    [XmlIgnore]
    public string Password { get; set; }
}

var serializer = new XmlSerializer(typeof(Person));
var person = new Person { Name = "Arvind", Age = 25 };

// Serialize → XML file
using var writer = new StreamWriter("person.xml");
serializer.Serialize(writer, person);
// <Person age="25"><FullName>Arvind</FullName></Person>

// Deserialize → object
using var reader = new StreamReader("person.xml");
Person? p = (Person?)serializer.Deserialize(reader);
```

---

#### 🟤 Binary Serialization
> Fastest, smallest output — but not human-readable. Use for caching, IPC, or internal data transfer.

```csharp
// Modern approach — using BinaryWriter / BinaryReader (manual)
// Writing binary
using var bw = new BinaryWriter(File.OpenWrite("data.bin"));
bw.Write("Arvind");   // string
bw.Write(25);          // int
bw.Write(92.5);        // double

// Reading binary
using var br = new BinaryReader(File.OpenRead("data.bin"));
string name = br.ReadString();   // "Arvind"
int    age  = br.ReadInt32();    // 25
double score = br.ReadDouble();  // 92.5

// Modern alternative — MessagePack or MemoryPack (NuGet)
// for high-performance binary serialization in production apps
```

**Serialization Comparison:**
| Format | Human-Readable | Speed | Size | Use Case |
|---|---|---|---|---|
| **JSON** | ✅ Yes | Fast | Medium | APIs, config, web |
| **XML** | ✅ Yes | Slow | Large | Legacy, SOAP, config |
| **Binary** | ❌ No | ⚡ Fastest | Small | Caching, IPC, perf-critical |

</details>

---

## 🗂️ Repository Structure

```
csharp-learning/
│
├── 📁 day1/                         ← Fundamentals
├── 📁 day2/                         ← Classes & Objects
├── 📁 day3/                         ← OOP 4 Pillars
├── 📁 day4/                         ← Basic Data Structures
├── 📁 day5/                         ← Generics
├── 📁 day6/                         ← Collections
│
├── 📁 day7/                         ← Exception & File Handling
│   ├── Exception-Handling/
│   │   ├── 01-try-catch-finally/
│   │   ├── 02-throw-vs-throw-ex/
│   │   ├── 03-Built-in-Exceptions/
│   │   └── 04-Global-Exception-Handling/
│   └── File-Handling/
│       ├── 01-StreamReader-StreamWriter/
│       ├── 02-File-and-Directory-Operations/
│       └── 03-Async-File-Handling/
│
├── 📁 day8/                         ← Expert I: Functional Programming & Delegates
│   ├── Functional-Programming/
│   │   ├── 01-Extension-Methods/
│   │   ├── 02-Lambda-Expressions/
│   │   ├── 03-LINQ/
│   │   ├── 04-Pattern-Matching/
│   │   └── 05-Immutability-PureFunctions-HOF/
│   ├── Delegates/
│   │   ├── 01-Action-Func-Predicate/
│   │   └── 02-Anonymous-Methods/
│   └── Events/
│       └── 01-Events-and-Event-Handling/
│
├── 📁 day9/                         ← Expert II: Multithreading, Async & Serialization
│   ├── Multithreading/
│   │   ├── 01-Thread-Class/
│   │   ├── 02-Task-Class/
│   │   └── 03-Parallel-ForEach/
│   ├── Async-Programming/
│   │   ├── 01-Async-and-Await/
│   │   ├── 02-Exception-Handling-in-Async/
│   │   └── 03-Async-Streams-IAsyncEnumerable/
│   └── Serialization/
│       ├── 01-JSON-Serialization/
│       ├── 02-XML-Serialization/
│       └── 03-Binary-Serialization/
│
└── 📄 README.md
```

---

## 🔜 Upcoming Topics

| # | Topic | Key Concepts |
|---|-------|-------------|
| 10 | **Expert III** | Reflection · Attributes · Expression Trees · Source Generators |
| 11 | **.NET Projects** | Console App · Web API · Entity Framework Core · Clean Architecture |

---

## 🛠️ Tools & Environment

| Tool | Version | Purpose |
|---|---|---|
| **Visual Studio** | 2026 | Primary IDE |
| **.NET SDK** | 10.0 | Runtime & tooling |
| **C#** | 14 | Language version |
| **Git** | Latest | Version control |

---

## 🚀 How to Use This Repo

```bash
# 1. Clone the repository
git clone https://github.com/arvind01A/csharp-learning.git
cd csharp-learning

# 2. Navigate to any day
cd day1/01-Variables

# 3. Run any .cs file
dotnet script Program.cs
# or
dotnet run
```

---

## 🤝 Contributing & Feedback

Found a mistake? Have a better explanation?

- ⭐ **Star** this repo if it helped you
- 🐛 **Open an issue** for corrections or suggestions
- 🍴 **Fork & PR** if you'd like to contribute notes

---

<div align="center">

Made with ❤️ and ☕ by [Arvind Kumar](https://github.com/arvind01A)

![Visitor Badge](https://visitor-badge.laobi.icu/badge?page_id=arvind01A.csharp-learning)

*"The best way to learn is to teach."* — Keep pushing forward! 🚀

</div>
