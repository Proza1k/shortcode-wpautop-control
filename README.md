# Shortcode wp-autop control

Allows you to turn off autop in individual shortcodes. It is inteded to be used within WordPress plugins and should not collide with other plugins that use it also.

In the past, if you created a shortcode, you had no way to stop wpautop from affecting the content within your shortcode. Now you can.

Usage:

```php
include "shortcode-wpautop-control.php";
chiedolabs_shortcode_wpautop_control(array('yourshortcode'));
```
## Example
To help you understand what this does, lets pretend we made a shortcode that outputs code blocks.

###Without this script
Input in the Wordpress editor:

```
[code]
<div>
	<div></div>
</div>
[/code]
```

Output in the browser:

```html
<div><br/>
	<div></div><br/>
</div><br/>
```

Notice how WordPress has added br tags we don't want?

###With this script
The top of your php file:

```
include "shortcode-wpautop-control.php";
chiedolabs_shortcode_wpautop_control(array('code'));
```

Input in the Wordpress editor:

```
[code]
<div>
	<div></div>
</div>
[/code]
```

Output in browser:

```
<div>
	<div></div>
</div>
```