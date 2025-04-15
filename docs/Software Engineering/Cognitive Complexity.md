---
share: true
---
[[Menschlicher Informationsspeicher|Menschlicher Informationsspeicher]]
[[../UI & UX/Interaktive Systeme/Superzeichenbildung (Chunking)|Superzeichenbildung (Chunking)]]

## Increments
- if, else if, else, ternary operator
- switch
- for, foreach
- while, do while
- catch
- sequences of binary logical operators
- each method in a recursion cycle
## Increase Nesting
- if, else if, else, ternary operator
- switch
- for, foreach
- while, do while
- catch
- nested methods and method-like structures such as lambdas
#### Nesting increments

These structures have additional increments based on the nesting levels
- if, ternary operator
- switch
- for, foreach
- while, do while
- catch
```java
@Nullable
private MethodJavaSymbol overriddenSymbolFrom(ClassJavaType classType) {
	if (classType.isUnknown()) { // +1
		return Symbols.unknownMethodSymbol;
	}

	boolean unknownFound = false;
	List<JavaSymbol> symbols = classType.getSymbol().members().lookup(name);
	for (JavaSymbol overrideSymbol : symbols) { // +1
		if (overrideSymbol.isKind(JavaSymbol.MTH) // +2 (nesting = 1)
			&& !overrideSymbol.isStatic()) { // +1
			MethodJavaSymbol methodJavaSymbol = (MethodJavaSymbol)overrideSymbol;
			if (canOverride(methodJavaSymbol)) { // +3 (nesting = 2)
				Boolean overriding = checkOverridingParameters(methodJavaSymbol, classType);
				if (overriding == null) {
					if (!unknownFound) { // +4 (nesting = 3)
						unknownFound = true; // +5 (nesting = 4)
					}
				} else if (overriding) { // +1
					return methodJavaSymbol;
				}
			}	
		}
	}
	if (unknownFound) { // +1
		return Symbols.unknownMethodSymbol;
	}
	return null;
} // summe = 19
```
