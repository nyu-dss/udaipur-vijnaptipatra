# udaipur-vijnaptipatra

proof of concept with [jekyll](https://jekyllrb.com), [mirador3](https://projectmirador.org/), and [wax_tasks](https://github.com/minicomp/wax_tasks).

## requirements
- `ruby >= 2.4` with `bundler`
- `imagemagick >= 6`
- `git`

## getting started

- Clone the demo:
  ```
  $ git clone https://github.com/nyu-dss/udaipur-vijnaptipatra
  $ cd udaipur-vijnaptipatra
  ```
- Bundle dependencies:
  ```
  $ bundle install
  ```
- Serve the site
  ```
  $ bundle exec jekyll serve
  ```

## to reproduce
- add source images to `_data/source_images/scroll` and name them in order as needed, e.g.,
  ```
  .
  └── _data/
      └── source_images/
          └── scroll/
              └── 00.png
              └── 01.png
              └── ... etc.
  ```
  (these are `.gitignored` due to file size; more info on setting up the project for derivative generation can be found here: https://minicomp.github.io/wiki/wax/preparing-your-collection-data/image-data/)

- destroy derivatives
  ```
  $ rm -rf img/derivatives
  ```
- rebuild derivatives
  ```
  $ bundle exec rake wax:derivatives:iiif scroll
  ```
- make sure index.md has the right manifest path in the YAML front matter
