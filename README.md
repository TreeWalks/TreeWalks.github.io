# TreeWalks.github.io
Website dedicated for the tree walk(s) of CSU Fresno campus

Source code of [CSU Fresno Tree Walk website](https://TreeWalks.github.io).
A new tree walk of the campus was designed to primarily include native, indigenous, and / or drought resistant specimens. This website shows the newly designed stops along with 360 photos and a companion augmented reality guide application.

## Companion app accompanies website

This is also a companion website to an [augmented reality Tree Walk Guide application](https://play.google.com/store/apps/details?id=dev.csaba.armap.treewalk) [(also open source)](https://github.com/TreeWalks/tree-walk-guide/). The application starts off with a hard coded initial path but immediately updates it to apply any correction made since the last app release. This way the app is operational in an off-line setting. The download consists of multiple interpolated XML files by the website which separates the localizable data from the non localizable data to avoid data duplication.

## Spinning out your own walk

You can easily spin out your own walk. You just need to modify the GPS locations and possibly the artwork in case your walk is not a tree walk but a different kind.
1. Each stop along the path is technically a Jekyll blog post. You want to modify the blog post date to reorder them (in the file name and the post's front end matter), insert or delete.
2. The blog posts mainly contain the texts which are localizable. For non localizable data, such as GPS coordinates, scientific name, height / width, etc. modify the [stops.yaml](https://github.com/TreeWalks/TreeWalks.github.io/blob/main/_data/stops.yaml) file which contains a corresponding entry for each "blog post" (a.k.a. stop) in a time sorted order.
3. You can decide to feature extra or different metadata if your tree walk has some different data or it's a different walk (not about trees). In case of metadata change you want to also update the mobile app accordingly. The mobile app downloads the data via xml files interpolated by this website:
4. The mobile app downloads [locations.xml](https://github.com/TreeWalks/TreeWalks.github.io/blob/main/locations.xml) for non localized metadata, and [locations_en.xml](https://github.com/TreeWalks/TreeWalks.github.io/blob/main/locations_en.xml) and [locations_es.xml](https://github.com/TreeWalks/TreeWalks.github.io/blob/main/locations_es.xml)
5. Optionally design different artwork: website color scheme (currently [red-indigo](https://github.com/TreeWalks/TreeWalks.github.io/blob/3f42a3b399576e60ab2763c035983a6c569e6b39/_config.yml#L20)), map marker logos, etc. I'm using [InkScape] for designing SVG and vectorial art, but it's all up to you what you prefer. You can also use non vectorial images, Google Maps JavaScript API can handle those natively, you just need to modify the marker placement code in [main_map.html](https://github.com/TreeWalks/TreeWalks.github.io/blob/3f42a3b399576e60ab2763c035983a6c569e6b39/_includes/main_map.html#L54) and [post_map.html](https://github.com/TreeWalks/TreeWalks.github.io/blob/3f42a3b399576e60ab2763c035983a6c569e6b39/_includes/post_map.html#L18)
6. Optionally add your own 3D augmented markers and objects. The helper classes are natively able to handle `obj` format objects. I'm using [Tinker CAD](https://www.tinkercad.com/) and [Blender](https://www.blender.org/), but it's all up to you, since you can use your preferred modeler or 3rd party tools to convert or export 3D objects into `obj` format. The `obj` format is human readable and you need to strip the mtl off of it, I do that manually.

Everything is open source so feel free to modify as you wish! Contact me if you have any questions!
