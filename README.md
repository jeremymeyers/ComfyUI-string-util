# ComfyUI String Utilities — nodes.py

This README documents the nodes defined in `nodes.py` (string utilities) and gives a short description of each node, its inputs and outputs, and notes for usage.

## Overview

The package provides small utility nodes for working with strings in ComfyUI node graphs. Each node is mapped in `NODE_CLASS_MAPPINGS` and displayed via `NODE_DISPLAY_NAME_MAPPINGS`.

## Nodes

- `string_util_Str` — "String Str"  
  - Description: Convert any object to its string representation.  
  - Inputs: `object` (any, optional)  
  - Outputs: `STRING` (string)

- `string_util_StrConcat` — "String Concat"  
  - Description: Concatenate two strings.  
  - Inputs: `s1` (STRING), `s2` (STRING)  
  - Outputs: `STRING` (s1 + s2)

- `string_util_StrEqual` — "String Equal"  
  - Description: Compare two strings for equality.  
  - Inputs: `s1` (STRING), `s2` (STRING)  
  - Outputs: `BOOLEAN` (s1 == s2)

- `string_util_StrNotEqual` — "String Not Equal"  
  - Description: Compare two strings for inequality.  
  - Inputs: `s1` (STRING), `s2` (STRING)  
  - Outputs: `BOOLEAN` (s1 != s2)

- `string_util_StrLen` — "String Length"  
  - Description: Return length of a string.  
  - Inputs: `s` (STRING)  
  - Outputs: `INT` (len(s))

- `string_util_StrLower` — "String Lower"  
  - Description: Return lowercase version of a string.  
  - Inputs: `s` (STRING)  
  - Outputs: `STRING` (s.lower())

- `string_util_StrUpper` — "String Upper"  
  - Description: Return uppercase version of a string.  
  - Inputs: `s` (STRING)  
  - Outputs: `STRING` (s.upper())

- `string_util_StrStrip` — "String Strip"  
  - Description: Strip whitespace from both ends.  
  - Inputs: `s` (STRING)  
  - Outputs: `STRING` (s.strip())

- `string_util_StrLstrip` — "String Lstrip"  
  - Description: Strip whitespace from the left.  
  - Inputs: `s` (STRING)  
  - Outputs: `STRING` (s.lstrip())

- `string_util_StrRstrip` — "String Rstrip"  
  - Description: Strip whitespace from the right.  
  - Inputs: `s` (STRING)  
  - Outputs: `STRING` (s.rstrip())

- `string_util_StrStartsWith` — "String StartsWith"  
  - Description: Test whether a string starts with a prefix.  
  - Inputs: `s` (STRING), `prefix` (STRING)  
  - Outputs: `BOOLEAN` (s.startswith(prefix))

- `string_util_StrEndsWith` — "String EndsWith"  
  - Description: Test whether a string ends with a suffix.  
  - Inputs: `s` (STRING), `suffix` (STRING)  
  - Outputs: `BOOLEAN` (s.endswith(suffix))

- `string_util_StrFind` — "String Find"  
  - Description: Find the index of a substring and indicate whether it was found.  
  - Inputs: `s` (STRING), `value` (STRING)  
  - Outputs: `INT` (`index` from `s.find(value)`), `BOOLEAN` (`found`)  
  - Note: The node's `found` output is computed as `index > 0`, so when the substring occurs at index 0, `found` will be False. (That may be unexpected; consider changing to `index >= 0` if you want index 0 to count as found.)

- `string_util_StrReplace` — "String Replace"  
  - Description: Replace occurrences of a substring with another.  
  - Inputs: `s` (STRING), `to_replace` (STRING), `replace_with` (STRING)  
  - Outputs: `STRING` (s.replace(to_replace, replace_with))

- `string_util_StrCount` — "String Count"  
  - Description: Count occurrences of a substring.  
  - Inputs: `s` (STRING), `value` (STRING)  
  - Outputs: `INT` (s.count(value))

- `string_util_StrJoin` — "String Join"  
  - Description: Join a list of strings using a separator.  
  - Inputs: `strings` (STRING list, `forceInput: True`), `sep` (STRING)  
  - Outputs: `STRING` (separator joined strings)  
  - Note: This node is configured as an input-list node (`INPUT_IS_LIST = True`). In the implementation it expects `sep` as a list and uses `sep[0]` as the actual separator — take care when wiring this node in the UI.

- `string_util_StrSplit` — "String Split"  
  - Description: Split a string into multiple string outputs using a separator.  
  - Inputs: `s` (STRING), `sep` (STRING)  
  - Outputs: list of `STRING` (split strings) — `OUTPUT_IS_LIST = (True,)`

- `string_util_StrSlice` — "String Slice"  
  - Description: Return substring using Python slice semantics.  
  - Inputs: `s` (STRING), `start` (INT), `end` (INT)  
  - Outputs: `STRING` (s[start:end])

- `string_util_StrFormat` — "String Format"  
  - Description: Format a string using Python's `str.format`. The node takes an optional `object` and a required `format` string.  
  - Inputs: `object` (any, optional), `format` (STRING)  
  - Outputs: `STRING` (format.format(object))

## Example usage notes

- `StrFormat` uses Python `str.format`, so format strings like `"Hello {}"` or `"Value: {0:.2f}"` work.
- `StrJoin` and `StrSplit` are useful for converting between lists and delimited strings inside graphs.
- Consider fixing the `StrFind` `found` logic if you need index 0 to be recognized as "found".

## Contributing

If you want to add, fix, or improve node behaviors (for example the `StrFind` found-flag), open a pull request with changes to `nodes.py` and update this README accordingly.
