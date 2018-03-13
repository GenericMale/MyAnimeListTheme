# MyAnimeList Theme

This is my custom theme for MyAnimeList (MAL).

## Preview

![Screenshot](docs/assets/screenshot.png?raw=true)

## Features

* Responsive
* Tested on Chrome, Firefox, IE11, Edge
* Support for custom headers and backgrounds using the MAL image selectors
* Uses MAL Modern Theme
* All controls still in place and fully functional (with the exception of the `More` button)
* Shows Title, Status (Watched, Planned etc), Episodes, Big Images, User Score, Season, Type (TV, Movie etc), Rating (PG-13, R etc)
* Additionally supports sorting by Aired Dates, Watched Dates, Storage, Priority

## Installation

1. In your MAL Account Settings open the Tab _List Style Design_, select _Modern_, click on the _Default Theme_ and hit _Save_.
2. Go to the _Lists_ tab and decide on which information to show. At least _Episodes_ and _Image_ is required. 
Optional but highly recommended is _Score_, _Premiered_, _Type_ and _Rating_.
Additionally the following fields will just give you additional sort options but the data is not shown in this theme:
_Aired Dates_, _Start/End Dates_, _Storage_ and _Priority_. Don't forget to click the _Submit_ button!
3. Go to _List Style Design_ again and click on the preview image of the _Default Theme_.
4. Set _Show cover image_ to _No_ and either set _Show background image_ to no or follow the steps outlined in *Custom Header Image* section to upload your own banner.
5. Expand _Add Custom CSS_ and paste in the following code and click save:
```css
@import url('https://malcat-gen.appspot.com/series?template=.data.image a[href^="/$list/$id/"]:after{background-image:url($series_image)}');
@import url('https://genericmale.github.io/MyAnimeListTheme/theme.css');
```

More info can be found on [Beginner Tutorial](https://myanimelist.net/forum/?topicid=1499052).

Note: it can take a few minutes until the high quality covers are generated.

### Custom Header Image

To use a custom header image, just upload it as cover image on the _Customize Default Theme_ page.

The default header provided with the theme has a size of 150px. To align all icons with the custom header, 
use the following as _Custom CSS_ and change the pixel size to the height of your header image:

```css
@import url('https://malcat-gen.appspot.com/series?template=.data.image a[href^="/$list/$id/"]:after{background-image:url($series_image)}');
@import url('https://genericmale.github.io/MyAnimeListTheme/theme.css');

.list-menu-float {
  top: 150px
}
```

## Building

This theme is developed using the Sass CSS precompiler. For more info go [sass-lang.com](https://sass-lang.com/)
The one and only source file for now is the _theme.scss_ in the _src_ directory (i might add a few other color variations of this theme in the future).
After running the sass compiler (see steps below), the final css is put into the _docs_ folder.

To compile the project follow these steps:
1. Install NodeJS and make sure `npm` is on your path.
2. Switch to the directory with the _package.json_ and run `npm install`.
3. Execute `npm run build`.

## TODO

* Show difference between chapters and volumes in manga list and fix height of status indicator
* Use css variables for customization
* Improve variables used in sass file to enable easier extension and customization
