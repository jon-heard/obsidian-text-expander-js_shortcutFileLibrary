Various random tables found on the web

Enter the shortcut "help tables" for reference.


~~
```
^help tables$
```
~~
```js
let result = "### TABLES SHORTCUTS HELP\n";
result += "- __help tables__ - Display this help text.\n";
result += "***\n";
result += "- __tbl twist__ - Roll a twist.  [Source](https://jvhouse.xyz/plot-twist-situations).\n";
return result + "\n";
```


~~
~~
```js
function roll(max) { return Math.trunc(Math.random() * max + 1); }
function aPick(a) { return a[roll(a.length)-1]; }
function aPickWeight(a, wIndex, theRoll)
{
	wIndex = wIndex || 1;
	theRoll = theRoll || roll(a.last()[wIndex]);
	for (let i = 0; i < a.length; i++)
	{
		if (a[i][wIndex] >= theRoll)
		{
			return a[i];
		}
	}
	return a.last();
}
```


~~
```
^tbl twist$
```
~~
```js
let target = ["ENVIRONMENT","ALLY","ENEMY","UNKNOWN","SOMETHING","INFORMATION"];
let circumstance = ["MISSING / GONE / LOST / FORGOTTEN","EXPLOSIVE / DANGEROUS / SENSITIVE","BLOCKED / HIDDEN / TRAPPED","ARRIVED / RECENT / NEW","DEAD / DESTROYED / UNRECOVERABLE","BROKEN / DAMAGED / INJURED","FLOODED / OVERFLOWED / EXCEEDED","SABOTAGED / CAPTURED / TAKEN","CORRUPTED / TWISTED / INSANE","FALSE / FAKE / LYING / TREASON","MISTAKEN / ERROR / FALSE / WRONG","LEAKED / DISCOVERED / KNOWN","ERRATIC / UNRELIABLE / FAILING / INSUFFICIENT","DISRUPTED / MODIFIED / ARTIFICIAL","SURPRISING / ALTERED / UNEXPECTED","YOUNGER / OLDER / NEWER / OBSOLETE","SICK / HAZARDOUS / POISON / TOXIC","PREPARED / ARMED / EXPECTING","UNPREPARED / UNARMED / UNEXPECTED","DELAYED / TIMED / WAIT"];
return [ "__Twist__\n", aPick(target), " - ", aPick(circumstance), "\n\n" ]

```