# ComfyUI String Util

String utility nodes for ComfyUI that provide comprehensive string manipulation and processing capabilities.

## Overview

This extension adds 19 custom nodes to ComfyUI, organized by category. Each node provides specific string operations ranging from simple transformations to complex text analysis.

---

## Node Reference

### Type Conversion

#### **String Str** (`string_util_Str`)
- **Purpose**: Converts any object to its string representation
- **Inputs**: `object` (optional, any type)
- **Outputs**: `string`
- **Description**: Takes any input object and converts it to a string format

---

### String Comparison

#### **String Equal** (`string_util_StrEqual`)
- **Purpose**: Compares two strings for exact equality
- **Inputs**: `s1` (string), `s2` (string)
- **Outputs**: `bool` (boolean)
- **Description**: Returns true if both input strings are identical

#### **String Not Equal** (`string_util_StrNotEqual`)
- **Purpose**: Checks if two strings are different
- **Inputs**: `s1` (string), `s2` (string)
- **Outputs**: `bool` (boolean)
- **Description**: Returns true if the input strings are not equal

---

### String Transformation

#### **String Concat** (`string_util_StrConcat`)
- **Purpose**: Concatenates two strings together
- **Inputs**: `s1` (string), `s2` (string)
- **Outputs**: `string`
- **Description**: Joins two strings end-to-end

#### **String Lower** (`string_util_StrLower`)
- **Purpose**: Converts string to lowercase
- **Inputs**: `s` (string)
- **Outputs**: `string`
- **Description**: Transforms all alphabetic characters to lowercase

#### **String Upper** (`string_util_StrUpper`)
- **Purpose**: Converts string to uppercase
- **Inputs**: `s` (string)
- **Outputs**: `string`
- **Description**: Transforms all alphabetic characters to uppercase

#### **String Strip** (`string_util_StrStrip`)
- **Purpose**: Removes leading and trailing whitespace
- **Inputs**: `s` (string)
- **Outputs**: `string`
- **Description**: Strips whitespace from both ends of the string

#### **String Lstrip** (`string_util_StrLstrip`)
- **Purpose**: Removes leading whitespace only
- **Inputs**: `s` (string)
- **Outputs**: `string`
- **Description**: Strips whitespace from the left (beginning) of the string

#### **String Rstrip** (`string_util_StrRstrip`)
- **Purpose**: Removes trailing whitespace only
- **Inputs**: `s` (string)
- **Outputs**: `string`
- **Description**: Strips whitespace from the right (end) of the string

---

### String Analysis

#### **String Length** (`string_util_StrLen`)
- **Purpose**: Gets the length of a string
- **Inputs**: `s` (string)
- **Outputs**: `length` (integer)
- **Description**: Returns the number of characters in the string

#### **String StartsWith** (`string_util_StrStartsWith`)
- **Purpose**: Checks if string starts with a prefix
- **Inputs**: `s` (string), `prefix` (string)
- **Outputs**: `bool` (boolean)
- **Description**: Returns true if the string starts with the specified prefix

#### **String EndsWith** (`string_util_StrEndsWith`)
- **Purpose**: Checks if string ends with a suffix
- **Inputs**: `s` (string), `suffix` (string)
- **Outputs**: `bool` (boolean)
- **Description**: Returns true if the string ends with the specified suffix

#### **String Find** (`string_util_StrFind`)
- **Purpose**: Searches for a substring within a string
- **Inputs**: `s` (string), `value` (string to find)
- **Outputs**: `index` (integer), `found` (boolean)
- **Description**: Returns the index of the first occurrence and a boolean indicating if found

#### **String Count** (`string_util_StrCount`)
- **Purpose**: Counts occurrences of a substring
- **Inputs**: `s` (string), `value` (string to count)
- **Outputs**: `count` (integer)
- **Description**: Returns the number of times the substring appears in the string

---

### String Manipulation

#### **String Replace** (`string_util_StrReplace`)
- **Purpose**: Replaces all occurrences of a substring
- **Inputs**: `s` (string), `to_replace` (string), `replace_with` (string)
- **Outputs**: `string`
- **Description**: Replaces all instances of the search string with the replacement string

#### **String Slice** (`string_util_StrSlice`)
- **Purpose**: Extracts a substring using indices
- **Inputs**: `s` (string), `start` (integer), `end` (integer)
- **Outputs**: `string`
- **Description**: Returns a substring from start index to end index

#### **String Split** (`string_util_StrSplit`)
- **Purpose**: Splits a string into an array
- **Inputs**: `s` (string), `sep` (separator string)
- **Outputs**: `strings` (array of strings)
- **Description**: Splits the string by the separator and returns an array of substrings

#### **String Join** (`string_util_StrJoin`)
- **Purpose**: Joins multiple strings with a separator
- **Inputs**: `strings` (list of strings), `sep` (separator string)
- **Outputs**: `string`
- **Description**: Joins an array of strings with the specified separator between them

#### **String Format** (`string_util_StrFormat`)
- **Purpose**: Formats a string with dynamic content
- **Inputs**: `object` (optional, any type), `format` (format string)
- **Outputs**: `string`
- **Description**: Uses Python string formatting to insert values into a template string

---

## Installation

1. Clone this repository into your ComfyUI `custom_nodes` directory
2. Restart ComfyUI
3. The string utility nodes will appear under the "string-util" category

## Usage Example

1. Add any string node to your workflow
2. Connect appropriate string inputs
3. Process the outputs in
