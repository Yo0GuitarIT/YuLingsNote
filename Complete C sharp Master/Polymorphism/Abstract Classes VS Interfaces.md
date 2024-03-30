# Abstract Classes VS Interfaces

**Abstract Classes** : A class designed to be inherited by subclasses.

**Interfaces** : An Interface is a contact.

### Similarties

- Cannot be instantiated.
- They both support Polymorphism.

### Key Differences

|                   Interface                   |                   Abstract classes                   |
| :-------------------------------------------: | :--------------------------------------------------: |
|             Not implement at all              | Either partially implemented or not inplement at all |
|            Can't have constructor             |                Can have constructors                 |
|  Contain only method declaration / No fields  |        May Contain motheds definitions,fields        |
| Classes can implement more than one interface |       Class can extend(Inherit) one class only       |
|    Classes must implement all its members     |     Classes must implement abstract members only     |

### Analogy

- Instuctor at Tutorials. EU
  - Instructor : abstract class
  - C# Instructor : concrete class
  - IVideo Editer : Interface

## When Shoud I choose Inheritance over an Interface when designing c# class libraries?

1. **抽象類別（Abstract Class）**：

   - 當你希望其子類別具有某些功能時，可以使用抽象類別。
   - 抽象類別中包含了一組函數，你希望子類別能夠擁有這些函數。
   - 抽象類別通常用於衍生類別與抽象類別共享核心屬性和行為的情況，這些行為實際上定義了類別的本質。

2. **介面（Interface）**：
   - 如果你只想要一個通用的契約或行為，可以使用介面。
   - 介面通常比抽象類別鬆散。
   - 不適合在所有介面方法中不斷重複相同的程式碼情況下使用介面。

使用抽象類別可以定義一次每個方法，當衍生類別與抽象類別具有相同的核心屬性和行為時，使用抽象類別。  
而使用介面時，你只需定義一組通用的契約或行為。

## Summary

1. **抽象類別（Abstract Class）**：

   - 當我們談論抽象類別時，我們定義了物件類型的特徵，明確指定了一個物件是什麼。
   - 換句話說，抽象類別定義了物件的本質。

2. **介面（Interface）**：
   - 當我們談論介面並定義了我們承諾提供的能力時，我們建立了關於物件能夠做什麼的契約。
   - 介面確定了物件可以執行的操作或功能，而不是定義物件的本質。

總結來說，抽象類別強調物件的特徵和本質，而介面則強調了物件能夠執行的操作或功能。
