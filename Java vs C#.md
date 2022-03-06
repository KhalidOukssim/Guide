# Java vs C#

```c#
using system;
namespace Exam01{
    class Exam{
        Static void main(String[] args){
            Console.WriteLine("hi");
        }
    }
}
```

```
Console.WriteLine("{0} {1}", a, b); //afficher a et b 
```

```c#
sealed class Program{ //canoot be inrited
    readonly int a;//canoot be changed
}
```

## C# projects

With Java, you basically could have a pile of .java files and then you could run a big command line command with javac and you'd get a .class file. If you were fancy, you'd use a compilation tool that would take care of invoking the Java compiler such as Ant, Maven, or Gradle. But these were independent technologies that simply invoked the Java compiler. With C#, there is a similar system, but they are already baked into the official Microsoft ecosystem. You could in theory run a manual csc (C# compile) commands from the command line, but no one really does that. Instead, there is a Solution file and a series of C# Project files (with file extensions of .sln and .csproj respectively).

**Solution (.sln) files** - This is basically just a list of related .csproj files.

**Project (.csproj) files** - This is the smallest individual compilation unit. A csproj file will get compiled into a .exe or .dll file. Additionally, they can have dependencies on other project files (which don't necessarily have to be C#). I'm hesitant to use the phrase "they're like Java packages". But they are somewhat similar.

msbuild (which comes with most modern Windows machines) can be pointed to a solution or project file and will know what to do. Most command line options can be encoded into the .csproj file itself (much like a make/ant file).

**Code (.cs) files** - Code belongs to a .csproj file. Code files can have any name. The name does not matter. Unlike Java where the filename must match the class contained within. This is not the case in C#. Although it's generally a good idea. Organizing files into subdirectories has absolutely no bearing on how the code is compiled. Namespaces (which are like package names) can be whatever you want regardless of where the file is located.

Execution of your program begins in a method called Main in a class called Program

## Style Convention

The following are just conventions. You can violate any of these if you're feeling stubborn, but if you ever plan on working with other people who have to read your code, I wouldn't recommend it.

- Classes are always capitalized, just like Java
- Methods are always capitalized, unlike Java
- Interfaces are always prefixed with an uppercase I
- Opening curly braces go on the next line
- Variables use **camelCase**, just like Java. Not **road_kill_case** like C++.
- However, unlike Java, Enum members are **PascalCase**, not upper **ROAD_KILL_CASE**.

## Termenology Diff

There are quite a number of language keywords that are identical across C# and Java with the exception of their name.

- package scoped classes and methods (i.e. the ones that you didn't declare as either private, public, or protected) have a keyword in C# called **internal**. These fields/classes are only visible to other code within the same csproj file.
- **final** is weird because it had multiple uses in Java. You could declare a class as final and that would mean you couldn't extend it. Alternatively you could set a field or variable as final which means you can't modify the value. For C#, a class that cannot be inherited from uses the **sealed** keyword. A field that you cannot modify uses the **readonly** keyword.

And if you're the sort of developer that just made everything mutable/extensible and only used public/private, then none of this really matters anyway, I guess.