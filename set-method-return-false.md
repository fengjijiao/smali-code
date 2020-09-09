```
public class EnabledTest {
    public static boolean isEnabled() {
        return false;
    }
}
```
# And then compile/dx/disassemble it  

```
javac EnabledTest.java
dx --dex --output=EnabledTest.dex EnabledTest.class
baksmali EnabledTest.dex
```
# And you'll end up with something like  

```
.method public static isEnabled()Z
    .registers 1
    const v0, 0
    return v0
.end method
```
