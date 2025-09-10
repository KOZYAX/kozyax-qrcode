# KozyaxQrcode - QR Code & Poster Generator

<div dir="rtl">

## ئۇيغۇرچە تونۇشتۇرۇش

بۇ PHP دا يېزىلغان QR كود ۋە پوستېر ياساش كۇتۇپخانىسى. بۇ كۇتۇپخانا ئۇيغۇر تىلىنى ئالاھىدە قوللايدۇ ۋە ئۇيغۇرچە تېكىست بىلەن QR كود ۋە پوستېر ياساشقا ئىمكان بېرىدۇ.

### ئالاھىدىلىكلىرى

- QR كود ياساش
- پوستېر ياساش 
- ئۇيغۇر تىلىنى قوللاش
- كۆپ خىل فونت قوللاش
- سۈرەت ئىشلەش ئىقتىدارى

### ئورنىتىش

```bash
composer require kozyax/kozyax-qrcode
```

### ئىشلىتىش مىسالى

```php
use KozyaxQrcode\QRcode;
use KozyaxQrcode\Uyghur;
use KozyaxQrcode\Poster;

// QR كود ياساش
QRcode::png('سالام ياخشىمۇ', 'qrcode.png');

// ئۇيغۇر تېكىستىنى ئۆزگەرتىش  
$uyghur = new Uyghur();
$processedText = $uyghur->getUyPFStr('سالام ياخشىمۇ');

// پوستېر ياساش
$config = [
    'bg_url' => 'background.jpg',
    'text2' => [
        [
            'text' => $processedText,
            'left' => 100,
            'top' => 200,
            'fontSize' => 50,
            'fontColor' => '255,255,255'
        ]
    ]
];

Poster::setConfig($config);
Poster::make('poster.png');
```

</div>

## English Introduction

A PHP library for generating QR codes and posters with special support for the Uyghur language. This library provides tools to create QR codes and posters with Uyghur text processing capabilities.

### Features

- QR Code generation
- Poster creation
- Uyghur language support
- Multiple font support  
- Image processing capabilities

### Installation

```bash
composer require kozyax/kozyax-qrcode
```

### Usage Example

```php
use KozyaxQrcode\QRcode;
use KozyaxQrcode\Uyghur;
use KozyaxQrcode\Poster;

// Generate QR Code
QRcode::png('Hello World', 'qrcode.png');

// Process Uyghur text
$uyghur = new Uyghur();
$processedText = $uyghur->getUyPFStr('سالام ياخشىمۇ');

// Create poster
$config = [
    'bg_url' => 'background.jpg',
    'text2' => [
        [
            'text' => $processedText,
            'left' => 100,
            'top' => 200,
            'fontSize' => 50,
            'fontColor' => '255,255,255'
        ]
    ]
];

Poster::setConfig($config);
Poster::make('poster.png');
```

## Requirements

- PHP >= 7.0
- GD Extension

## License

This project is licensed under the LGPL-3.0 License.

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## Classes

### QRcode
Main class for generating QR codes with various customization options.

### Uyghur  
Handles Uyghur text processing and font rendering for proper display.

### Poster
Creates posters with text and image elements, supporting multiple text layers and fonts.

## Fonts

The library includes several Uyghur fonts:
- UKIJMoyQB.ttf
- Nurjanbay TalTal Tom2.0.TTF
- LATINWD.TTF
- iqbal bulaq.ttf
- Uyghur Microsoft Uighur.ttf
