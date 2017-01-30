# README

* Download [ImageMagick](http://imagemagick.org/script/download.php#macosx)
    * I recommend downloading [MacPorts](https://www.macports.org/install.php) first and then running `sudo port install ImageMagick`
    * Using Homebrew doesn't update the necessary dependencies as easily and was a huge headache

* Paperclip cares about the security of your app like no one else does! Starting from version 4, it is required to have at least a content type validation in your model
    * But, what if we’re seasoned developers and can take care of ourselves? Can we tell Paperclip that our attachments should not be validated? But, of course:
    * `do_not_validate_attachment_file_type :avatar`
 


## Resources

* [SitePoint tutorial](https://www.sitepoint.com/uploading-files-with-paperclip/)
* [RMagick Docs](https://rmagick.github.io/usage.html)
* [ImageMagick Download](http://imagemagick.org/script/download.php#macosx) 
* [MacPorts Download](https://www.macports.org/install.php)
* [Paperclip Docs](https://github.com/thoughtbot/paperclip)