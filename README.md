# ArrayToExcel [![NuGet version](https://badge.fury.io/nu/ArrayToExcel.svg)](http://badge.fury.io/nu/ArrayToExcel)
Create Excel from Array

### Example #1

```C#
var items = Enumerable.Range(1, 10).Select(x => new
{
    Prop1 = $"Text #{x}",
    Prop2 = x * 1000,
    Prop3 = DateTime.Now.AddDays(-x),
});

var excel = items.ToExcel();
```

![](/Examples/example1.png)
[example1.xlsx](Examples/example1.xlsx?raw=true)

### Example #2

```C#
var excel = items.ToExcel(x => x
    .AddColumn("MyColumnName#1", x => x.Prop1)
    .AddColumn("MyColumnName#2", x => $"test:{x.Prop2}")
    .AddColumn("MyColumnName#3", x => x.Prop3));
```

![](/Examples/example2.png)
[example2.xlsx](Examples/example2.xlsx?raw=true)

[More info in the test console application...](TestConsoleApp/Program.cs)