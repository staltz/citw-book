# Flexbox

React Native's style system looks like CSS, but it has its differences. To begin with, there are no `display: inline`, no `display: inline-block`, no `width: 100%`, etc. Instead, React Native supports Flexbox, which turns out is enough to accomplish most layouts you wish, including 100% width and so forth. You can assume that by all components have `display: flex` by default, and in fact there is only `display: flex` and `display: none`.

## flexDirection

With Flexbox, you need to first define the **direction** of a container: `row` (lay out children horizontally) or `column` (lay out children vertically). This direction is known as the "primary axis" of the Flexbox.

```
+-----------------------------------------+
|            flexDirection: row           |
|                                         |
|+------+-------+------------+-----+-----+|
||      |       |            |     |     ||
|+------+-------+------------+-----+-----+|
+-----------------------------------------+
```

```
+----------------------+
|  flexDirection: row  |
|                      |
|+--------------------+|
||                    ||
||                    ||
|+--------------------+|
||                    ||
||                    ||
||                    ||
||                    ||
|+--------------------+|
||                    ||
||                    ||
||                    ||
|+--------------------+|
||                    ||
||                    ||
||                    ||
||                    ||
|+--------------------+|
+----------------------+
```

## justifyContent

To change the positioning of the children along the flex direction (the primary axis), use justifyContent, which supports the values:

- `'flex-start'`: all children near the beginning of the parent
- `'center'`: all children grouped together in the center of the parent
- `'flex-end'`: all children near the end of the parent
- `'space-around'`, `'space-between'`, `'space-evenly'`: gradually distribute the children along the primary axis of the parent

```
+-----------------------------------------+
|            flexDirection: row           |
|        justifyContent: flex-start       |
|                                         |
|+------+-------+------+                  |
||      |       |      |                  |
|+------+-------+------+                  |
+-----------------------------------------+
```

```
+-----------------------------------------+
|            flexDirection: row           |
|         justifyContent: flex-end        |
|                                         |
|                  +------+-------+------+|
|                  |      |       |      ||
|                  +------+-------+------+|
+-----------------------------------------+
```

```
+-----------------------------------------+
|            flexDirection: row           |
|         justifyContent: center          |
|                                         |
|         +------+-------+------+         |
|         |      |       |      |         |
|         +------+-------+------+         |
+-----------------------------------------+
```

```
+-----------------------------------------+
|            flexDirection: row           |
|      justifyContent: space-between      |
|                                         |
|+------+        +-------+        +------+|
||      |        |       |        |      ||
|+------+        +-------+        +------+|
+-----------------------------------------+
```

```
+-----------------------------------------+
|            flexDirection: row           |
|      justifyContent: space-evenly       |
|                                         |
|    +------+    +-------+    +------+    |
|    |      |    |       |    |      |    |
|    +------+    +-------+    +------+    |
+-----------------------------------------+
```

```
+-----------------------------------------+
|            flexDirection: row           |
|      justifyContent: space-around       |
|                                         |
|   +------+     +-------+     +------+   |
|   |      |     |       |     |      |   |
|   +------+     +-------+     +------+   |
+-----------------------------------------+
```

## alignItems

To control the positioning of the *other* axis perpendicular to the primary axis, use alignItems, which supports the values:

- `'flex-start'`: all children near the beginning of the secondary axis of the parent
- `'center'`: all children near the center of the secondary axis of the parent
- `'flex-end'`: all children near the end of the secondary axis of the parent
- `'stretch'`: **instead of positioning the children on the secondary axis, _stretch_ their size to fit the total secondary axis size**

```
+-----------------------------------------+
|            flexDirection: row           |
|        justifyContent: flex-start       |
|          alignItems: flex-start         |
|+------+-------+------+                  |
||      |       |      |                  |
|+------+-------+------+                  |
|                                         |
|                                         |
|                                         |
|                                         |
+-----------------------------------------+
```

```
+-----------------------------------------+
|            flexDirection: row           |
|        justifyContent: flex-start       |
|            alignItems: center           |
|                                         |
|                                         |
|+------+-------+------+                  |
||      |       |      |                  |
|+------+-------+------+                  |
|                                         |
|                                         |
+-----------------------------------------+
```

```
+-----------------------------------------+
|            flexDirection: row           |
|        justifyContent: flex-start       |
|           alignItems: flex-end          |
|                                         |
|                                         |
|                                         |
|                                         |
|+------+-------+------+                  |
||      |       |      |                  |
|+------+-------+------+                  |
+-----------------------------------------+
```

```
+-----------------------------------------+
|            flexDirection: row           |
|        justifyContent: flex-start       |
|            alignItems: stretch          |
|+------+-------+------+                  |
||      |       |      |                  |
||      |       |      |                  |
||      |       |      |                  |
||      |       |      |                  |
||      |       |      |                  |
|+------+-------+------+                  |
+-----------------------------------------+
```

## Tips

**width 100%**: if you want to have the children essentially do `width: 100%`, then you probably need to use `alignItems: 'stretch'`, which in the case of width means you need to set these styles on the parent:

- `flexDirection: 'column'`
- `alignItems: 'stretch'`
- `justifyContent` doesn't make a difference

**height 100%**: you need to set these styles on the parent:

- `flexDirection: 'row'`
- `alignItems: 'stretch'`
- `justifyContent` doesn't make a difference

**Fill the remaining space**: if some children have fixed sizes but one child should fill all the remaining space, then you can use `flex: 1` which stretches that child along the **primary axis**, see diagram below:

```
+-----------------------------------------+
|            flexDirection: row           |
|+------+-------------------------+------+|
||      |         flex: 1         |      ||
|+------+-------------------------+------+|
+-----------------------------------------+
```