在 C# 中，基类方法如果要被重写，除了 `virtual` 和 `abstract`，还可以使用以下关键字：

1. **virtual**：基类中的方法使用 `virtual` 关键字声明，表示该方法可以在子类中被重写。 
   
   - 示例：
     ```csharp
     public class BaseClass
     {
         public virtual void ShowMessage()
         {
             Console.WriteLine("BaseClass Message");
         }
     }
     ```
   
2. **abstract**：基类中的方法使用 `abstract` 关键字声明，表示该方法必须在派生类中实现，但在基类中没有具体实现。声明类时，类也必须是抽象类（`abstract`）。
   - 示例：
     ```csharp
     public abstract class BaseClass
     {
         public abstract void ShowMessage();
     }
     ```

3. **override**：用于在子类中重写基类的虚方法或抽象方法，方法签名必须与基类方法一致。
   - 示例：
     ```csharp
     public class DerivedClass : BaseClass
     {
         public override void ShowMessage()
         {
             Console.WriteLine("DerivedClass Message");
         }
     }
     ```

4. **sealed**：用于阻止进一步的重写。可以将 `sealed` 关键字应用于重写的方法上，表示该方法不能再在派生类中被重写。
   - 示例：
     ```csharp
     public class DerivedClass : BaseClass
     {
         public sealed override void ShowMessage()
         {
             Console.WriteLine("DerivedClass Message");
         }
     }
     ```

5. **new**：用于隐藏基类中的成员，而不是重写。如果子类成员和基类成员具有相同的签名，但不是重写关系，可以使用 `new` 关键字显示隐藏基类的成员。
   - 示例：
     ```csharp
     public class BaseClass
     {
         public virtual void ShowMessage()
         {
             Console.WriteLine("BaseClass Message");
         }
     }
     
     public class DerivedClass : BaseClass
     {
         public new void ShowMessage()
         {
             Console.WriteLine("DerivedClass Message");
         }
     }
     ```

### 总结

| 关键字     | 作用                                                 |
| ---------- | ---------------------------------------------------- |
| `virtual`  | 用于在基类中声明可被重写的方法。                     |
| `abstract` | 用于在基类中声明必须被重写且没有实现的方法。         |
| `override` | 用于在子类中重写基类中的虚方法或抽象方法。           |
| `sealed`   | 用于防止在派生类中进一步重写 `override` 方法。       |
| `new`      | 用于隐藏基类成员，而不是重写（通常不建议频繁使用）。 |

这些关键字帮助开发者定义和控制方法的继承和重写行为，实现多态性和类的灵活性。