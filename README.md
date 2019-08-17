### spotbugs
---
https://github.com/spotbugs/spotbugs

```java
//spotbugs/src/main/java/edu/umd/cs/findbugs/BugAccumulator.java
package edu.umd.cs.findbugs;

import java.util.HashMap;

public class BugAccumulator {
 
  private final BugReporter reporter;
  
  private final boolean performAccumulation;
  
  public void reportBug(BugInstance bug, Data d) {
    bug.setPriority(d.priority);
    bug.addSourceLine(d.primarySource);
    HashSet<Integer> lines = new HashSet<>();
    lines.add(d.primarySource.getStartLine());
    d.allSource.remove(d.primarySource);
    for (SourceLineAnnotation source : d.allSource) {
      if (lines.add(source.getStartLine())) {
        bug.addSourceLine(source);
        bug.describe(SourceLineAnnotation.ROLE_ANOTHER_INSTANCE);
      }
    }
  }
  
  
}


```

```
```

```
```
