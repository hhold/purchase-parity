# purchase-parity

A library to calculate purchasing price parity. 

## Installation

Use the package manager [npm](https://www.npmjs.com/package/purchase-parity) to install.

```bash
npm i purchase-parity
```

## Usage

```js
const parity = require('purchase-parity');

/* Input price in USD and alpha2 code of destination country,
returns price in destination currency */
parity.getPrice(5, 'IN')  
// 100

// Returns the rate for a country
parity.getRate('IN') 
// 19.9780782714

// Returns all available info on destination country
parity.getInfo('IN') 
/* {
  alpha3: 'IND',
  currencyCode: 'INR',
  countryName: 'India',
  currencyName: 'Indian Rupee',
  minorUnit: 2,
  currency_numeric_code: 356,
  rate: 19.9780782714,
  alpha2: 'IN'
} */

```
### Error behaviour

All functions accept an optional parameter **throwError** which is **false** by default. If the alpha2 country code provided as input is invalid or if data is not available, then all functions except getRate and getPrice will return **undefined**, while getPrice will return the provided USD value itself and getRate will return 1. To throw an error instead in such cases, pass **throwError** with value **true**.

## Contributing
Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change.

Please make sure to update tests as appropriate.

## To Do

- write tests
- improve documentation
- migrate to typescript

## License
[MIT](https://choosealicense.com/licenses/mit/)
