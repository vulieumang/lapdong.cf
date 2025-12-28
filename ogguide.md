# Hướng Dẫn Tạo Open Graph Image Bằng SVG

## Tổng Quan

Phương pháp này sử dụng **SVG (Scalable Vector Graphics)** để tạo Open Graph image cho website. SVG có nhiều ưu điểm:
- ✅ Vector graphics - sắc nét ở mọi kích thước
- ✅ Dung lượng nhẹ (thường < 10KB)
- ✅ Hỗ trợ tốt trên Facebook, Twitter, LinkedIn
- ✅ Không cần tool screenshot hay image editor
- ✅ Dễ chỉnh sửa bằng text editor

## Kích Thước Chuẩn

**Open Graph Image Standard:**
- Width: 1200px
- Height: 630px
- Aspect Ratio: 1.91:1

## Template SVG Cơ Bản

```svg
<svg xmlns="http://www.w3.org/2000/svg" width="1200" height="630" viewBox="0 0 1200 630">
  <defs>
    <!-- Gradient background -->
    <linearGradient id="bgGrad" x1="0%" y1="0%" x2="100%" y2="100%">
      <stop offset="0%" style="stop-color:#YOUR_COLOR_1;stop-opacity:1" />
      <stop offset="50%" style="stop-color:#YOUR_COLOR_2;stop-opacity:1" />
      <stop offset="100%" style="stop-color:#YOUR_COLOR_3;stop-opacity:1" />
    </linearGradient>
    
    <!-- Glow effect (optional) -->
    <filter id="glow">
      <feGaussianBlur stdDeviation="4" result="coloredBlur"/>
      <feMerge>
        <feMergeNode in="coloredBlur"/>
        <feMergeNode in="SourceGraphic"/>
      </feMerge>
    </filter>
  </defs>
  
  <!-- Background -->
  <rect width="1200" height="630" fill="url(#bgGrad)"/>
  
  <!-- Decorative elements -->
  <circle cx="100" cy="100" r="200" fill="white" opacity="0.1"/>
  <circle cx="1100" cy="530" r="150" fill="white" opacity="0.1"/>
  
  <!-- Content box -->
  <rect x="200" y="120" width="800" height="390" rx="30" 
        fill="rgba(0,0,0,0.2)" 
        stroke="rgba(255,255,255,0.3)" 
        stroke-width="3"
        filter="url(#glow)"/>
  
  <!-- Main title -->
  <text x="600" y="220" 
        font-family="Arial, sans-serif" 
        font-size="72" 
        font-weight="900" 
        fill="white" 
        text-anchor="middle">
    YOUR TITLE HERE
  </text>
  
  <!-- Subtitle -->
  <text x="600" y="280" 
        font-family="Arial, sans-serif" 
        font-size="36" 
        font-weight="600" 
        fill="white" 
        text-anchor="middle">
    Your Subtitle Here
  </text>
  
  <!-- Additional info -->
  <text x="600" y="450" 
        font-family="Arial, sans-serif" 
        font-size="24" 
        fill="white" 
        text-anchor="middle">
    Additional Information
  </text>
</svg>
```

## Các Bước Thực Hiện

### Bước 1: Tạo File SVG

```bash
# Tạo file og-image.svg trong thư mục website
touch og-image.svg
```

### Bước 2: Chỉnh Sửa Nội Dung

Mở file `og-image.svg` và thay đổi:
1. **Colors**: Thay `#YOUR_COLOR_1`, `#YOUR_COLOR_2`, `#YOUR_COLOR_3`
2. **Title**: Thay "YOUR TITLE HERE"
3. **Subtitle**: Thay "Your Subtitle Here"
4. **Additional Info**: Thêm thông tin liên hệ, slogan, etc.

### Bước 3: Thêm Meta Tags Vào HTML

```html
<head>
  <!-- Favicon -->
  <link rel="icon" type="image/svg+xml" href="favicon.svg">
  
  <!-- Open Graph / Facebook -->
  <meta property="og:type" content="website">
  <meta property="og:url" content="https://yourdomain.com/">
  <meta property="og:title" content="Your Page Title">
  <meta property="og:description" content="Your page description">
  <meta property="og:image" content="https://yourdomain.com/og-image.svg">
  <meta property="og:image:width" content="1200">
  <meta property="og:image:height" content="630">
  <meta property="og:locale" content="vi_VN">
  
  <!-- Twitter Card -->
  <meta name="twitter:card" content="summary_large_image">
  <meta name="twitter:url" content="https://yourdomain.com/">
  <meta name="twitter:title" content="Your Page Title">
  <meta name="twitter:description" content="Your page description">
  <meta name="twitter:image" content="https://yourdomain.com/og-image.svg">
</head>
```

## Ví Dụ Thực Tế

### Ví Dụ 1: Portfolio Website (Pink Theme)

```svg
<svg xmlns="http://www.w3.org/2000/svg" width="1200" height="630">
  <defs>
    <linearGradient id="pinkGrad" x1="0%" y1="0%" x2="100%" y2="100%">
      <stop offset="0%" style="stop-color:#ff1493"/>
      <stop offset="50%" style="stop-color:#ff69b4"/>
      <stop offset="100%" style="stop-color:#ffd700"/>
    </linearGradient>
  </defs>
  
  <rect width="1200" height="630" fill="url(#pinkGrad)"/>
  
  <text x="600" y="300" 
        font-family="Arial" 
        font-size="80" 
        font-weight="900" 
        fill="white" 
        text-anchor="middle">
    YOUR NAME
  </text>
  
  <text x="600" y="380" 
        font-family="Arial" 
        font-size="40" 
        fill="white" 
        text-anchor="middle">
    Web Designer &amp; Developer
  </text>
</svg>
```

### Ví Dụ 2: Business Website (Blue Theme)

```svg
<svg xmlns="http://www.w3.org/2000/svg" width="1200" height="630">
  <defs>
    <linearGradient id="blueGrad" x1="0%" y1="0%" x2="100%" y2="100%">
      <stop offset="0%" style="stop-color:#1e3a8a"/>
      <stop offset="100%" style="stop-color:#3b82f6"/>
    </linearGradient>
  </defs>
  
  <rect width="1200" height="630" fill="url(#blueGrad)"/>
  
  <text x="600" y="280" 
        font-family="Arial" 
        font-size="70" 
        font-weight="900" 
        fill="white" 
        text-anchor="middle">
    COMPANY NAME
  </text>
  
  <text x="600" y="360" 
        font-family="Arial" 
        font-size="35" 
        fill="white" 
        text-anchor="middle">
    Professional Business Solutions
  </text>
</svg>
```

## Customization Tips

### 1. Thay Đổi Màu Sắc

```svg
<!-- Gradient 2 màu -->
<linearGradient id="grad">
  <stop offset="0%" style="stop-color:#START_COLOR"/>
  <stop offset="100%" style="stop-color:#END_COLOR"/>
</linearGradient>

<!-- Gradient 3 màu -->
<linearGradient id="grad">
  <stop offset="0%" style="stop-color:#COLOR_1"/>
  <stop offset="50%" style="stop-color:#COLOR_2"/>
  <stop offset="100%" style="stop-color:#COLOR_3"/>
</linearGradient>
```

### 2. Thêm Logo/Icon

```svg
<!-- Emoji as icon -->
<text x="600" y="180" font-size="80" text-anchor="middle">🚀</text>

<!-- Or use image -->
<image href="logo.png" x="500" y="100" width="200" height="200"/>
```

### 3. Thêm Decorative Elements

```svg
<!-- Circles -->
<circle cx="100" cy="100" r="150" fill="white" opacity="0.1"/>

<!-- Rectangles -->
<rect x="50" y="50" width="200" height="200" fill="white" opacity="0.1" rx="20"/>

<!-- Lines -->
<line x1="0" y1="315" x2="1200" y2="315" stroke="white" stroke-width="2" opacity="0.2"/>
```

### 4. Typography Styles

```svg
<!-- Bold Title -->
<text font-weight="900" font-size="80">Bold Title</text>

<!-- Light Subtitle -->
<text font-weight="300" font-size="30" opacity="0.9">Subtitle</text>

<!-- Italic -->
<text font-style="italic">Italic Text</text>

<!-- Letter Spacing -->
<text letter-spacing="5">Spaced Text</text>
```

## Testing

### 1. Preview Locally

```bash
# Mở file SVG trong browser
open og-image.svg
```

### 2. Test Social Media Preview

**Facebook Debugger:**
https://developers.facebook.com/tools/debug/

**Twitter Card Validator:**
https://cards-dev.twitter.com/validator

**LinkedIn Post Inspector:**
https://www.linkedin.com/post-inspector/

## Common Issues & Solutions

### Issue 1: SVG không hiển thị trên Facebook

**Solution:** Một số platform không hỗ trợ SVG. Convert sang PNG:

```bash
# Sử dụng ImageMagick (nếu đã cài)
convert og-image.svg og-image.png

# Hoặc sử dụng online converter
# https://cloudconvert.com/svg-to-png
```

### Issue 2: Text bị cắt

**Solution:** Kiểm tra `viewBox` và đảm bảo text nằm trong bounds:

```svg
<svg viewBox="0 0 1200 630">
  <!-- Ensure text x,y are within 0-1200 and 0-630 -->
</svg>
```

### Issue 3: Font không hiển thị đúng

**Solution:** Sử dụng web-safe fonts hoặc embed font:

```svg
<defs>
  <style>
    @import url('https://fonts.googleapis.com/css2?family=Inter:wght@400;700;900');
  </style>
</defs>

<text font-family="Inter, Arial, sans-serif">Text</text>
```

## Quick Reference: Color Palettes

### Professional
```
Blue: #1e3a8a → #3b82f6
Green: #065f46 → #10b981
Purple: #5b21b6 → #a855f7
```

### Creative
```
Pink: #ff1493 → #ff69b4 → #ffd700
Orange: #ff4400 → #ff8800
Sunset: #ff6b6b → #ffd93d → #6bcf7f
```

### Dark/Modern
```
Dark Blue: #0f172a → #1e293b
Dark Purple: #1e1b4b → #4c1d95
Gradient: #000000 → #434343
```

## Checklist

- [ ] Tạo file `og-image.svg` với kích thước 1200x630
- [ ] Thêm gradient background phù hợp với brand
- [ ] Thêm title, subtitle, và thông tin cần thiết
- [ ] Thêm decorative elements (circles, shapes)
- [ ] Test hiển thị trong browser
- [ ] Thêm meta tags vào HTML
- [ ] Test với Facebook Debugger
- [ ] Test với Twitter Card Validator
- [ ] (Optional) Convert sang PNG nếu cần

## Resources

- **SVG Tutorial:** https://developer.mozilla.org/en-US/docs/Web/SVG/Tutorial
- **Color Picker:** https://coolors.co/
- **Gradient Generator:** https://cssgradient.io/
- **Font Awesome (Icons):** https://fontawesome.com/

---

**Lưu ý:** File này được tạo dựa trên phương pháp đã sử dụng thành công cho website minhthanh.cf. Bạn có thể tùy chỉnh và mở rộng theo nhu cầu của từng project!
