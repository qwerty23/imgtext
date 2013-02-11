
Introduction
------------

IMGText is a PHP library that generates a PNG image for each word in a string,
and then generates HTML markup to display those images as if they were text.
[Also available in Korean](http://github.com/kijin/imgtext/blob/master/README.KO.md).

Most of the time, Western text on the Web can be easily stylized with web fonts.
Since the majority of Western writing systems contain only a few dozen glyphs,
web fonts tend to be small -- a few dozen KB -- and thus quick to download.
This is unfortunately not the case for a lot of Asian scripts, such as Korean,
Japanese, and Chinese (both traditional and simplified). These languages
contain thousands of glyphs, resulting in web fonts that are several MB in size.

As a result, many Asian web designers are stuck with OS default fonts,
or resort to images. (Other options, such as <canvas>, is rarely used because
the affected countries also have a major infestation of outdated browsers.)
The former looks hideous, especially at large font sizes used in headings.
The latter, on the other hand, suffers from several disadvantages:

  - Each image needs to be created by hand, and it is difficult to maintain
    consistency in font size, color, etc. over a long time.
  - Search engines and screen readers cannot access the original text,
    unless each image is accompanied by corresponding alt-text,
    which again needs to be created by hand.
  - Text can be easily re-flowed when the screen is resized,
    but images can only be zoomed, leading to broken layout and/or
    poor legitibility in mobile devices.

IMGText is meant to solve these problems, not by addressing the source of
the problems (lack of usable web fonts for Asian scripts), but by acknowledging
the sad reality and automating image generation and use as much as possible.

  - Given a string, a font, and some options such as font size and color,
    IMGText generates a PNG image for each word in the string,
    and also generates HTML markup to display them as if they were text.
    You only need to take the HTML markup and place it in your pages.
  - Since each word is turned into a separate image, the result can be
    easily re-flowed just like plain text.
  - Additional styling can be applied by using CSS and/or JavaScript
    on <img> tags with the "imgtext" class.
  - Each image is accompanied by corresponding alt-text, making the result
    readable by search engines and screen readers.
  - The annoying hover effect in Internet Explorer is also taken care of.

IMGText is most beneficial when used in headings. It is not recommended for
body text, which can easily become a mess with hundreds of small images.

IMGText requires PHP 5 and GD. All text must be encoded in UTF-8.

IMGText is released under the MIT license. It is freely available for
personal, non-profit, commercial, governmental, and any other use.
