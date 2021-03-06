# enum-values

Library for getting the names and values of typescript enum

## Installation
```
npm install enum-values --save
```


### Example in TypeScript
```javascript
  import { EnumValues } from 'enum-values';

  // Suppose we have an numeric and a string valued enum
  enum NumericEnum {
    VALUE1,
    VALUE2,
    VALUE3
  }

  enum StringEnum {
    VALUE4 = 'V4',
    VALUE5 = 'V5'
  }

  // names will be equal to: ['VALUE1', 'VALUE2', 'VALUE3']
  var names1 = EnumValues.getNames(NumericEnum);

  // names will be equal to: ['VALUE4', 'VALUE5']
  var names2 = EnumValues.getNames(StringEnum);

  // values will be equal to: [0, 1, 2]
  var values1 = EnumValues.getValues(NumericEnum);

  // values will be equal to: ['V4', 'V5']
  var values2 = EnumValues.getValues(StringEnum);

  // namesAndValues will be equal to:
  // [
  //  { name: 'VALUE1', value: 0 },
  //  { name: 'VALUE2', value: 1 },
  //  { name: 'VALUE3', value: 2 }
  // ]
  var namesAndValues1 = EnumValues.getNamesAndValues(NumericEnum);

  // namesAndValues will be equal to:
  // [
  //  { name: 'VALUE4', value: 'V4' },
  //  { name: 'VALUE5', value: 'V5' }
  // ]
  var namesAndValues2 = EnumValues.getNamesAndValues(StringEnum);
```

## Known issues
Currently the library does not support mixing string and numeric enums.

```javascript
// This enum will not work:
enum MixedEnum {
  A = 'A',
  1 = 2,
  3 = 'B',
  C = 4
}
```