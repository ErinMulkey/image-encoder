# image-encoder
*Brief*: An attempt at encoding messages using particular pixels of an image.

## Methodology
Given a key `K`, override particular pixels of an image to hold characters of text. Using the 256 possible values of the red, green and blue values of a pixel, respectively, one may fit a block of 4 characters of a 64-letter alphabet in a single pixel.

Zero-index the image's pixels from top-left to bottom-right, row by row. Let `N` be the number of pixels present. Choose `K` as a number coprime with `N`, and some initial offset `I`.

The `j`-th block of characters may be found in the `(I + j*K) % N`-th pixel. Signify the end of a message with some decided character. A maximum of `N` blocks of characters may be encoded with this method.

The key `K` **must** be coprime with the number of pixels `N` to ensure no collisions with already-encoded pixels in the encoding process.