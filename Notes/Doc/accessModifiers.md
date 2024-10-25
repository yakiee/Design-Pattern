### 1. **public**

- **描述**：该成员可以被任何其他代码访问，不受任何限制。

- **示例**：

  ```csharp
  public class MyClass { }
  ```

### 2. **private**

- **描述**：该成员只能在定义它的类内部访问，其他类无法访问。

- **示例**：

  ```csharp
  class MyClass
  {
      private int myField; // 只能在 MyClass 中访问
  }
  ```

### 3. **protected**

- **描述**：该成员可以在任何派生类中都可访问，其他程序集可访问。

- **示例**：

  ```csharp
  class BaseClass
  {
      protected int myField; // 可以在派生类中访问
  }
  
  class DerivedClass : BaseClass
  {
      void SomeMethod()
      {
          myField = 5; // 可以访问
      }
  }
  ```

### 4. **internal**

- **描述**：该成员可以在同一程序集内的任何代码中访问，其他程序集内不可访问。

- **示例**：

  ```csharp
  internal class MyClass { } // 只能在同一程序集访问
  ```

### 5. **protected internal**

- **描述**：该成员可以在同一程序集内的任何代码中访问，其他程序集的派生类可以访问。

- **示例**：

  ```csharp
  class MyClass
  {
      protected internal int myField; // 在同一程序集和派生类中可访问
  }
  ```

### 6. **private protected**

- **描述**：该成员只能在定义它的类及其派生类中访问，其他程序集内不可访问。

- **示例**：

  ```csharp
  class MyClass
  {
      private protected int myField; // 只能在同一程序集的派生类中访问
  }
  ```
