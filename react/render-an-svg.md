# Render An SVG

__Category: React__

SVG files are a good choice for use as icons or logos as they provide support for scaling and have a small file size  compared to a PNG or JPEG image.

The following code will load an SVG from the filesystem and render it in a React component:

```javascript
import { default as logo } from './assets/icons/logo.svg';

export default ImageContainer = () => {
  return (
    <div>
      <img src={logo} width='120' height='40' alt='Logo'/>
    </div>
  )
}
```
