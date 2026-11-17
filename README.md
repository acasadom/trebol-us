# trebol-us

The rules of a form for [Trebol](https://github.com/acasadom/trebol): ZIP codes and Social Security numbers.

```sh
npm install trebol-us
```

A program that imports the package writes the rules after its fields, as it writes `email`:

```trebol
import 'trebol-us

view [
    form [
        field code "ZIP code" required zip
        field id "SSN" ssn
        submit "Save" [toast "Saved"]
    ]
]
```

| Rule   | Function | What it takes |
| ------ | ------ | --- |
| `zip`  | `zip?` | five digits, or ZIP+4: `94103`, `94103-1234` |
| `ssn`  | `ssn?` | a Social Security number: `123-45-6789`, the dashes optional |

An SSN has no part all zeros, and does not start with 666 or from 900. The rules check that the value is
well made, not that it exists. Each message is in English and Spanish, and an app may change it in `i18n/ui`, as any other.

The functions work without forms too: `zip? "94103-1234"` is true.

## Tests

```sh
npm test
```
