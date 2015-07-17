# rack-facebook-signed-request

Rack middleware which parses and verifies the signed_request canvas parameter and FB JS cookie.

See [Facebook's Canvas Documentation](http://developers.facebook.com/docs/authentication/canvas) for more details.

### Required Options

You must specify the following options to enable the middleware:

* `app_id`
* `secret`

### Additional Custom Options

You can also activate the following options:

* `inject_facebook` (default: false): This will automatically inject the asynchronous FB JS SDK include into the response body.

Assuming you've enabled the Facebook script injection, you can customize these options:

* `cookie` (default: true): Configure the FB JS SDK with cookie support
* `status` (default: true)
* `lang` (default: 'en_US')
* `xfbml` (default: true)

Note that this will also add the FB XML namespace attribute into the root html element of the response.

### RESTful behavior

The Rack middleware will also convert any POST requests containing the `signed_request` parameter to GET.