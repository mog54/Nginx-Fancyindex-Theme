# Nginx-Fancyindex-Theme
A responsive theme for [Nginx](https://www.nginx.org/) Fancyindex module. Minimal, modern and simple.
Comes with a search form, aims to handle thousands of files without any problems.

The fancyindex module can be found [here](https://github.com/aperezdc/ngx-fancyindex) (by @aperezdc).

[![made-for-nginx](https://img.shields.io/badge/Made%20for-nginx-1f425f.svg)](https://www.nginx.org/)


Clone the repository

    git clone https://github.com/mog54/Nginx-Fancyindex-Theme.git


## Usage

1. Make sure you have the fancyindex module compiled with nginx, either by compiling it yourself or installing nginx via the full distribution (paquet `nginx-extras`).
2. Include the content of [fancyindex.conf](fancyindex.conf) in your location directive (`location / {.....}`) in your nginx config (usually `nginx.conf`).
3. Move the `Nginx-Fancyindex-Theme-light/` *and/or* `Nginx-Fancyindex-Theme-dark/` folder to the root of the site directory.
4. Restart/reload nginx.
5. Check that it's working, and enjoy!
6. A new feature is the automatic inclusion of `HEADER.md` and `README.md` file from the current directory (if any), as shown in the example above. It uses [JQuery](https://jquery.com/) and [ShowDown.js](https://github.com/showdownjs/showdown/), it is not so cleanly written but it works perfectly! I wanted this feature as I have it for Apache (see [this project](https://bitbucket.org/lbesson/autoindex-strapdown)).

## Configuration

A standard config looks something like this (use `-light` for the default light theme, or `-dark` for a dark theme):

```bash
fancyindex on;
fancyindex_localtime on;
fancyindex_exact_size off;
fancyindex_header "/Nginx-Fancyindex-Theme-dark/header.html";
fancyindex_footer "/Nginx-Fancyindex-Theme-dark/footer.html";
fancyindex_ignore "examplefile.html"; # Ignored files will not show up in the directory listing, but will still be public. 
fancyindex_ignore "Nginx-Fancyindex-Theme-dark"; # Making sure folder where files are don't show up in the listing. 
# Warning: if you use an old version of ngx-fancyindex, comment the last line if you
# encounter a bug. See https://github.com/Naereen/Nginx-Fancyindex-Theme/issues/10
#fancyindex_name_length 255; # Maximum file name length in bytes, change as you like.
```
