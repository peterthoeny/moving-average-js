# Moving average algorithms & demo (moving-average-js)

[![GitHub issues](https://img.shields.io/github/issues/peterthoeny/moving-average-js)](https://github.com/peterthoeny/moving-average-js/issues)
[![GitHub stars](https://img.shields.io/github/stars/peterthoeny/moving-average-js)](https://github.com/peterthoeny/moving-average-js/stargazers)
[![GitHub license](https://img.shields.io/github/license/peterthoeny/moving-average-js)](https://github.com/peterthoeny/moving-average-js/blob/main/LICENSE)

## Getting Started

```
  $ git clone https://github.com/peterthoeny/moving-average-js.git # or clone your own fork
```
Point your browser to `moving-average-js/demo.html`.

Function usage example:
```
    let dataPoints = [ 2, 2, 3, 3, 4, 4, 5, 8, 9, 7, 5, 4, 4, 5, 4 ];
    let type = 'SMA';
    let size = 11;
    let sma = movingAverage(dataPoints, type, size);
    // expected: [ 2, 2, 2.3, 2.5, 2.8, 3, 3.3, 3.9, 4.4, 4.7, 4.7, 4.9, 5.1, 5.3, 5.4 ]
```

## Moving Average Documentation

The `movingAverage()` function in the `moving-average.js` Javascript file returns a moving average array from an input array of data points. Three types of classic moving averages are implemented:
- `SMA`: Simple moving average
- `EMA`: Exponential moving average
- `WMA`: Weighted moving average

A classic moving average algorythm looks only at a moving window (sample width) of data points to the left. Therfore, the moving average lags behind the current data point by half the sample width, e.g. the moving average curve is shifted to the right. This method is mainly used in financial applications.

In turn, a balanced moving average algorythm looks equally to the left and right of the current data point. In other words, the moving average is centered around the current data point. This is primarily used in scientific applications.

The balanced moving average algorythm in this implementation extends the given data point array by extrapolating the data points on both sides, assuming the same slope as the data points of half of the sample width on the left side and right side of the given input. This results in a better balanced start and end of the moving average curve. The demo depicts the extended slope on the left and right side.

Three types of balanced moving averages are implemented:
- `BSMA`: Balanced simple moving average
- `BEMA`: Balanced exponential moving average
- `BWMA`: Balanced weighted moving average

In addition, the slope over all data points is available with this type:
- `Slope`: Linear slope over all data points

## Demo

The `demo.html` file demonstrates the various moving average algorythms, also available online at (https://peterthoeny.github.io/moving-average/demo.html)[https://peterthoeny.github.io/moving-average/demo.html]

## Package Files

- `LICENSE` - MIT license file
- `README.md` - documentation
- `package.json` - package definition
- `moving-average.js` - JavaScript file with `movingAverage()` function
- `demo.htl` - HTML file to demo various moving average algorithms
- `demo.js` - JavaScript file with charting functions
- `screenshot.png` - Screenshot of demo

// EOF
