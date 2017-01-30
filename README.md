# README

## Requirements

* ImageMagick
* Paperclip gem
* Rails 4.2 or higher
* Ruby 2.0 or higher

## Steps

* Create a new Rails app
* Add nav bar to application.html.erb
* Add a Photos controller
* Set up the routes
* Add your model and migration
* migrate
* Integrate paperclip gem
* Bundle
* add attributes to photos table
    * `rails generate paperclip photo image`
* migrate
* add paperclip functionality to model
    * `has_attached_file :image`
* set up controller
    * just have to permit `image`
    * other fields are taken care of in paperclip
* create view for `new` action
    * use `f.file_field :image`
* extract errors to a partial in views/shared_errors.html.erb
* Paperclip requires content type validation
    ````validates_attachment :image,
                     content_type: { content_type: ["image/jpeg", "image/gif", "image/png"] }
    ````
* you are now ready to upload your first file
* create index view
    * iterate over @photos array
    * `views/photos/_photo.html.erb` partial will be used by default
* generate thumbnails with ImageMagick 

### Notes

* Download [ImageMagick](http://imagemagick.org/script/download.php#macosx)
    * I recommend downloading [MacPorts](https://www.macports.org/install.php) first and then running `sudo port install ImageMagick`
    * Using Homebrew didn't update the necessary dependencies as easily and was a huge headache

* Paperclip cares about the security of your app like no one else does! Starting from version 4, it is required to have at least a content type validation in your model
    * But, what if we’re seasoned developers and can take care of ourselves? Can we tell Paperclip that our attachments should not be validated? But, of course:
    * `do_not_validate_attachment_file_type :avatar`

## Resources

* [SitePoint Paperclip tutorial](https://www.sitepoint.com/uploading-files-with-paperclip/)
* [RMagick Docs](https://rmagick.github.io/usage.html)
* [ImageMagick Download](http://imagemagick.org/script/download.php#macosx) 
* [MacPorts Download](https://www.macports.org/install.php)
* [Paperclip Docs](https://github.com/thoughtbot/paperclip)