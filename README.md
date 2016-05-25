# Matrix ![](https://travis-ci.org/Clarence-pan/Matrix.svg)
Matrix - yet another tool for operating arrays, especially two-dimensional arrays.

# Usage
Provided a data source containing two columns - productId and productName, if only rows whose productId is bigger than 5 are needed, and if a key-value structure (key is productName) is needed, it can be solved like this:
```
$data = Matrix::from($dataSource)
      ->select(array('productId' => 'id', 'productName'))
      ->where(function ($row) {
          return $row['id'] > 5;
      })
      ->orderBy('id', SORT_DESC)
      ->indexedBy('productName')
      ->toArray();
```
