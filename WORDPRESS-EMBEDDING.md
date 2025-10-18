# WordPress Embedding Guide

This guide shows you how to embed the SPD Langenselbold Quiz into your WordPress website using an iframe.

## Prerequisites

1. GitHub Pages must be enabled for your repository
2. The quiz should be live at: `https://cbraunfi.github.io/SPD135Quiz/`
3. Your WordPress site must allow custom HTML/iframe embedding

## Method 1: Basic iframe (Simple)

Add this code to any WordPress page or post (using the HTML/Code editor):

```html
<iframe
  src="https://cbraunfi.github.io/SPD135Quiz/"
  width="100%"
  height="800"
  frameborder="0"
  scrolling="auto"
  title="SPD Langenselbold Jubiläums-Quiz">
</iframe>
```

## Method 2: Responsive iframe (Recommended)

This version automatically adjusts height and looks better on mobile devices:

```html
<div style="position: relative; width: 100%; max-width: 1000px; margin: 0 auto;">
  <iframe
    src="https://cbraunfi.github.io/SPD135Quiz/"
    style="width: 100%; height: 900px; border: 1px solid #e5e7eb; border-radius: 12px; box-shadow: 0 4px 12px rgba(0,0,0,0.1);"
    frameborder="0"
    scrolling="auto"
    title="SPD Langenselbold Jubiläums-Quiz">
  </iframe>
</div>
```

## Method 3: Full-width responsive with auto-height

For a more seamless integration that adjusts to content:

```html
<style>
  .spd-quiz-container {
    position: relative;
    width: 100%;
    max-width: 1000px;
    margin: 24px auto;
    padding: 0 16px;
  }
  .spd-quiz-iframe {
    width: 100%;
    min-height: 800px;
    border: 1px solid #e5e7eb;
    border-radius: 12px;
    box-shadow: 0 4px 12px rgba(0,0,0,0.1);
  }
  @media (max-width: 768px) {
    .spd-quiz-iframe {
      min-height: 1000px;
    }
  }
</style>

<div class="spd-quiz-container">
  <iframe
    src="https://cbraunfi.github.io/SPD135Quiz/"
    class="spd-quiz-iframe"
    frameborder="0"
    scrolling="auto"
    title="SPD Langenselbold Jubiläums-Quiz">
  </iframe>
</div>
```

## WordPress Instructions

### Using Gutenberg (Block Editor)

1. Edit your page/post
2. Click the **+** button to add a new block
3. Search for **"Custom HTML"** or **"HTML"** block
4. Paste one of the iframe codes above
5. Click **Preview** to test
6. Click **Publish** or **Update**

### Using Classic Editor

1. Edit your page/post
2. Switch to the **Text** tab (not Visual)
3. Paste one of the iframe codes above
4. Switch back to **Visual** to preview
5. Click **Publish** or **Update**

### Using a Page Builder (Elementor, Divi, etc.)

1. Add an **HTML widget** or **Code block**
2. Paste one of the iframe codes above
3. Save and preview

## Troubleshooting

### iframe not showing

- Check if your WordPress theme/security plugin blocks iframes
- Try adding this to your theme's functions.php (or use a plugin like "Code Snippets"):

```php
add_filter('wp_kses_allowed_html', function($tags, $context) {
    if ($context === 'post') {
        $tags['iframe'] = array(
            'src'             => true,
            'height'          => true,
            'width'           => true,
            'frameborder'     => true,
            'allowfullscreen' => true,
            'style'           => true,
            'class'           => true,
            'title'           => true,
            'scrolling'       => true,
        );
    }
    return $tags;
}, 10, 2);
```

### Height issues

- Adjust the `height` or `min-height` values to fit your content
- Mobile devices might need more height (use media queries as shown in Method 3)

### Security warnings

- GitHub Pages uses HTTPS, so your WordPress site should also use HTTPS
- Some security plugins might block external iframes - add `cbraunfi.github.io` to your allowlist

## Advanced: Custom Shortcode

For easier reuse, create a WordPress shortcode:

1. Add to your theme's `functions.php` or use "Code Snippets" plugin:

```php
function spd_quiz_shortcode() {
    return '<div style="position: relative; width: 100%; max-width: 1000px; margin: 0 auto;">
        <iframe
            src="https://cbraunfi.github.io/SPD135Quiz/"
            style="width: 100%; height: 900px; border: 1px solid #e5e7eb; border-radius: 12px; box-shadow: 0 4px 12px rgba(0,0,0,0.1);"
            frameborder="0"
            scrolling="auto"
            title="SPD Langenselbold Jubiläums-Quiz">
        </iframe>
    </div>';
}
add_shortcode('spd_quiz', 'spd_quiz_shortcode');
```

2. Then use this in any page/post:

```
[spd_quiz]
```

## Testing

After embedding:
- Test on desktop and mobile devices
- Check scrolling behavior
- Verify the quiz loads correctly
- Test all quiz functionality (buttons, confetti, share features)

## Notes

- The iframe loads the entire quiz from GitHub Pages
- Users stay on your WordPress site (the quiz appears embedded)
- Quiz data and functionality remain independent
- Share features will generate links to the GitHub Pages URL (you can customize this in the quiz code if needed)
