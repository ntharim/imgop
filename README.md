# imgop

Image-optimisation server powered by `libvips`

## Installation

```
npm install imgop
```

## Requirements

- `libvips`

## How it works

- Retrieve images from an s3 bucket
- Cache downloaded images to the file system for subsequent renders using `fs-lru-cache`
- Tesize and adjust image quality using parameters added to the querystring

## Usage

  Set the following environment variables:

  ```
  AWS_ACCESS_KEY_ID
  AWS_SECRET_ACCESS_KEY
  IMGOP_BUCKET
  PORT // optional - default is 3000
  ```

  Run server:

  ```
  node index.js
  ```

  Modify an image by adding parameters to the querystring:

  ```
  /example.jpg?w=1050&h=700&q=75&fit=crop&fm=png
  ```

## API

Similar to [`imgix`](http://www.imgix.com/docs/reference) with only the following parameters supported.

### `w`

Width.

### `h`

Height.

### `q`

Quality. Default is `80`.

### `fit`

Fit mode. `max` or `crop`. Default is `max`.

### `fm`

Format. `jpg`, `png` or `webp`. Default is `jpg`.

## Credits

[sharp](https://github.com/lovell/sharp)
[simgr](https://github.com/mgmtio/simgr)
