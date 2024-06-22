# ICU Format

## Overview
[ICU (International Components for Unicode)](https://unicode-org.github.io/icu/) is a widely-used library providing robust support for internationalization (i18n) and localization (l10n) in software applications. ICU Format is particularly useful for handling complex message formatting, including pluralization, date and time formatting, and variable substitution.

## Usage
ICU Format messages are structured using patterns enclosed within `{}` braces, with specific syntax for different types of formatting, such as plurals and dates. Here’s a brief overview of the components:

- **Variables**: Enclosed within `{}` braces, variables represent dynamic values substituted into the message.
- **Pluralization**: Used to handle plural forms based on a numeric value.
- **Date and Time**: Formats dates and times according to specified styles (e.g., `long`, `short`, `medium`).

## Example
Consider the following example in `en-US.json`:

```json
{
  "hello": "Hello World!",
  "demo": "{name} took {numPhotos, plural, =0 {no photos} =1 {one photo} other {# photos}} on {takenDate, date, long}."
}
```

String Literal ("hello"):

- "hello": "Hello World!" - This is a straightforward string translation where "hello" is the key and "Hello World!" is the corresponding translated message. No variables or formatting directives are used here.

Message Format ("demo"):
- {name} - Represents a variable placeholder that will be substituted with an actual name value.
- {numPhotos, plural, ...} - Handles pluralization based on the value of numPhotos.
    - ,=0 {no photos} - If numPhotos equals 0, it outputs "no photos".
    - , =1 {one photo} - If numPhotos equals 1, it outputs "one photo".
    - , other {# photos} - For all other numeric values of numPhotos, it outputs "# photos", where # is replaced with the actual number.
- {takenDate, date, long} - Formats the takenDate variable as a long date format.

## Resources
More examples can be found in this [lang folder of this repository](https://github.com/TranslateRN/i18n-examples/tree/main/format-icu/lang).

- [ICU User Guide](https://unicode-org.github.io/icu/userguide/format_parse/messages/) for the specification of ICU Message Format.
- [A Practical Guide to the ICU Message Format](https://phrase.com/blog/posts/guide-to-the-icu-message-format/) by Mohammad Ashour on Phrase Blog