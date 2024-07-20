# bc-ProfanityBlock
Profanity blocking JS script.

<img src="https://github.com/The-Best-Codes/bc-ProfanityBlock/assets/106822363/be4a2b9e-22bf-4173-9c54-7ac8456dd257" alt="icon" for="cover" />


# Functions

## Class: ContentFilterBadWord

A JavaScript class that provides methods for filtering and cleaning text to block or sanitize profanity.

### Constructor

```javascript
constructor()
```

- Initializes an instance of the `ContentFilterBadWord` class.
- Sets up the encoded bad words and evasion patterns.

### Properties

- `encodedCussWords` (Array): An array of base64 encoded bad words.
- `evasionPatterns` (Array): An array of evasion patterns used for normalizing text.

### Methods

#### `decodeBase64(encodedString)`

```javascript
decodeBase64(encodedString: string): string
```

- Decodes a base64 encoded string.
- Parameters:
  - `encodedString` (string): The base64 encoded string to decode.
- Returns:
  - The decoded string.

#### `normalizeText(text)`

```javascript
normalizeText(text: string): string
```

- Applies evasion patterns to normalize text.
- Parameters:
  - `text` (string): The text to normalize.
- Returns:
  - The normalized text.

#### `containsBadWords(text, matchWord = false, detectEvasionCharacters = true, detectEvasionSeperators = true)`

```javascript
containsBadWords(
  text: string,
  matchWord: boolean = false,
  detectEvasionCharacters: boolean = true,
  detectEvasionSeperators: boolean = true
): boolean
```

- Checks if the given text contains any bad words.
- Parameters:
  - `text` (string): The text to check for bad words.
  - `matchWord` (boolean, optional): Determines if the bad word should be matched as a whole word. Defaults to `false`.
  - `detectEvasionCharacters` (boolean, optional): Determines if evasion characters should be detected and normalized. Defaults to `true`.
  - `detectEvasionSeperators` (boolean, optional): Determines if evasion separators should be detected and removed. Defaults to `true`.
- Returns:
  - `true` if any bad words are found, otherwise `false`.

#### `cleanText(text, method = "replace", detectEvasionCharacters = true, detectEvasionSeparators = true)`

```javascript
cleanText(
  text: string,
  method: string = "replace",
  detectEvasionCharacters: boolean = true,
  detectEvasionSeparators: boolean = true
): string
```

- Cleans the given text by replacing or removing bad words.
- Parameters:
  - `text` (string): The text to clean.
  - `method` (string, optional): The cleaning method, either `"replace"` or `"remove"`. Defaults to `"replace"`.
  - `detectEvasionCharacters` (boolean, optional): Determines if evasion characters should be detected and normalized. Defaults to `true`.
  - `detectEvasionSeparators` (boolean, optional): Determines if evasion separators should be detected and removed. Defaults to `true`.
- Returns:
  - The cleaned text.

# Usage
## Usage Examples

Assuming `Cat`, `Dog`, and `Mountain` are bad words.

### Example 1: Checking if Text Contains Bad Words

```javascript
const filter = new ContentFilterBadWord();

const text = "I love my pet cat and dog!";
const containsBadWords = filter.containsBadWords(text);

console.log(containsBadWords);
// Output: true
```

In this example, we create an instance of the `ContentFilterBadWord` class. We then check if the given text contains any bad words using the `containsBadWords` method. Since the text contains the words "cat" and "dog," the output is `true`.

### Example 2: Cleaning Text by Replacing Bad Words

```javascript
const filter = new ContentFilterBadWord();

const text = "I hate my cat and dog!";
const cleanedText = filter.cleanText(text);

console.log(cleanedText);
// Output: "I hate my *** and ***!"
```

In this example, we clean the given text by replacing bad words with asterisks using the `cleanText` method. The output is a sanitized version of the text where the bad words "cat" and "dog" are replaced with asterisks.

### Example 3: Cleaning Text by Removing Bad Words

```javascript
const filter = new ContentFilterBadWord();

const text = "I hate my cat and dog!";
const cleanedText = filter.cleanText(text, "remove");

console.log(cleanedText);
// Output: "I hate my and !"
```

In this example, we clean the given text by removing bad words using the `cleanText` method with the `"remove"` method parameter. The output is a sanitized version of the text where the bad words "cat" and "dog" are removed.

### Example 4: Checking if Text Contains Bad Words with Evasion Characters

```javascript
const filter = new ContentFilterBadWord();

const text = "I h@t3 my c@t and d0g!";
const containsBadWords = filter.containsBadWords(text, false, true);

console.log(containsBadWords);
// Output: true
```

In this example, we check if the given text contains any bad words with evasion characters using the `containsBadWords` method with the `detectEvasionCharacters` parameter set to `true`. The output is `true` because the text contains the words "cat" and "dog" with evasion characters.

### Example 5: Checking if Text Contains Bad Words without Evasion Separators

```javascript
const filter = new ContentFilterBadWord();

const text = "Ihatemycatanddog";
const containsBadWords = filter.containsBadWords(text, false, false, true);

console.log(containsBadWords);
// Output: true
```

In this example, we check if the given text contains any bad words without evasion separators using the `containsBadWords` method with the `detectEvasionSeperators` parameter set to `true`. The output is `true` because the text contains the words "cat" and "dog" without any separators.


# About
This library is developed and maintained by [BestCodes](https://the-best-codes.github.io?github_profanityblock_repo). Contact the owner via best-codes@proton.me for more information.
