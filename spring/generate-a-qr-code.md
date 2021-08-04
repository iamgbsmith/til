# Generate A QR Code

__Category: Spring__

You can generate a QR Code in Spring Boot using the Zebra Crossing (ZXing) library and a simple `RestController`.

### Gradle dependencies

Add the following dependencies to your `build.gradle` file:

```shell
dependencies {
	implementation 'org.springframework.boot:spring-boot-starter-web'
	implementation 'com.google.zxing:core:3.4.1'
	implementation 'com.google.zxing:javase:3.4.1'
	testImplementation 'org.springframework.boot:spring-boot-starter-test'
}
```

### Buffered image converter

Create a HttpMessageConverter which converts a response object in the controller endpoint to a BufferedImage.

```java
package com.orbiks.qrcode;

import org.springframework.context.annotation.Bean;
import org.springframework.context.annotation.Configuration;
import org.springframework.http.converter.BufferedImageHttpMessageConverter;
import org.springframework.http.converter.HttpMessageConverter;

import java.awt.image.BufferedImage;

@Configuration
public class BufferedImageConverter {

    @Bean
    public HttpMessageConverter<BufferedImage> httpMessageConverter() {
        return new BufferedImageHttpMessageConverter();
    }

}

```

### Controller endpoint

Create a controller with an endpoint which accepts params for the text and size of the QR code. In this example, if the `size` query string parameter isn't supplied, it will default to 200 x 200 pixels.

The method should return a PNG.

```java
package com.orbiks.qrcode.controllers;

import com.google.zxing.BarcodeFormat;
import com.google.zxing.client.j2se.MatrixToImageWriter;
import com.google.zxing.common.BitMatrix;
import com.google.zxing.qrcode.QRCodeWriter;
import org.springframework.http.MediaType;
import org.springframework.web.bind.annotation.GetMapping;
import org.springframework.web.bind.annotation.RequestMapping;
import org.springframework.web.bind.annotation.RequestParam;
import org.springframework.web.bind.annotation.RestController;

import java.awt.image.BufferedImage;
import java.util.Optional;

@RestController
@RequestMapping(path = "/api/v1")
public class QrCodeGeneratorController {

    @GetMapping(path = "/qrcode", produces = MediaType.IMAGE_PNG_VALUE)
    public BufferedImage generateQRCodeImage(@RequestParam Optional<Integer> size, @RequestParam String text) throws Exception {
        QRCodeWriter qrCodeWriter = new QRCodeWriter();
        BitMatrix bitMatrix = qrCodeWriter.encode(text, BarcodeFormat.QR_CODE, size.orElse(200), size.orElse(200));
        return MatrixToImageWriter.toBufferedImage(bitMatrix);
    }

}
```

Go to the controller endpoint using a browser or Postman, specifying the value of the `text` query string parameter to embed in the QR code.

http://localhost:8080/api/v1/qrcode?size=250&text=https://www.porsche.com
