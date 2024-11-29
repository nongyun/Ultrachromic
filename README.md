## 超级色彩
这是色彩主题传奇的最终形态，真正的进化！旧的三部曲色彩主题已不再使用，因为它们的效果可以通过超级色彩来复现。

这是一个针对Jellyfin媒体服务器定制的CSS覆盖主题。请注意，我维护这个主题以确保与我当前使用的Jellyfin版本兼容，通常是最新稳定版。所以你可以假设在旧版本上使用此主题可能无法正常工作，但同时，如果新版本破坏了某些功能，我会修复它。如果你发现未主题化元素或有故障，请报告问题。

![Untitled](https://user-images.githubusercontent.com/4365015/127774204-03957527-7178-4ea2-8674-d83fe6a97d1c.png)

<br />

## 功能
- 主题化所有内容
- 三种样式可选
- 广泛的附加选项
- 可自定义强调色
- 自定义背景模糊程度
- 方形或圆角界面
- 进度条、封面页、背景、标识等选项
- 在移动设备上表现良好，紧凑对齐的用户界面
- 对原生UI的各种微调和修复

## 如何使用
要使用此主题，复制预设之一，或遵循创建自定义组合的说明，将其粘贴到“控制台>常规>自定义CSS”中并保存，它会立即全局应用于所有用户，叠加在他们正在使用的任何主题之上。要删除主题，请清除“自定义CSS”字段然后保存。

在预设后添加模块可能会导致功能不正常，如果你尝试这样做而不起作用，请不要打开问题报告。要么使用预设，要么使用自定义组合，不要混用，因为这不是我要测试和保证其有效性的使用情况。

注意：通过反向代理使用时，主题可能无法正常工作，请查看此README底部获取更多信息。

<br />

## 单行预设

这些让你能通过几个预设来使用超级色彩，它们保持了旧的色彩主题的外观。

```css
@import url('https://cdn.jsdelivr.net/gh/CTalvio/Ultrachromic/presets/monochromic_preset.css');
```
或者
```css
@import url('https://cdn.jsdelivr.net/gh/CTalvio/Ultrachromic/presets/kaleidochromic_preset.css');
```
或者
```css
@import url('https://cdn.jsdelivr.net/gh/CTalvio/Ultrachromic/presets/novachromic_preset.css');
```
只需要一行代码，nova和kaleido支持自定义强调色。

<br />
<br />

## 多行导入实现自定义

超级色彩由多个“部分”组成，允许你仅主题化你想要的部分，并对如何主题化有一定的选择。只需按照此处列出的顺序逐一添加导入。只需省略你不打算使用的部分。

<br />

### 1. 推荐

fixes.css包含JF UI各处的一些小调整，如这里的对齐，那里的大小微调。jf_font.css会让JF使用与其标志相同的字体。你可以两者都用，只用一个，或都不用。

```css
@import url('https://cdn.jsdelivr.net/gh/CTalvio/Ultrachromic/fixes.css');
@import url('https://cdn.jsdelivr.net/gh/CTalvio/Ultrachromic/jf_font.css');
```

<br />

### 2. 必需

以下css为必需项

```css
@import url('https://cdn.jsdelivr.net/gh/CTalvio/Ultrachromic/base.css');
@import url('https://cdn.jsdelivr.net/gh/CTalvio/Ultrachromic/accentlist.css');
```

<br />

### 3. 圆角

如果你想修改界面上的圆角，包括其中的一个，circlehover会在悬停时保持默认圆形高亮，否则高亮将是其他所有事物的圆角方形。

```css
@import url('https://cdn.jsdelivr.net/gh/CTalvio/Ultrachromic/rounding.css');
```
或者
```css
@import url('https://cdn.jsdelivr.net/gh/CTalvio/Ultrachromic/rounding_circlehover.css');
```

<br />

### 4. 更小的演员列表

![image](https://user-images.githubusercontent.com/4365015/127768495-3f211a57-3147-4b11-a9e0-5c9bdebc32b0.png)

较小的、正方形比例的演员列表样式。

```css
@import url('https://cdn.jsdelivr.net/gh/CTalvio/Ultrachromic/smallercast.css');
```

<br />

### 5. 紧凑剧集列表

![image](https://user-images.githubusercontent.com/4365015/127768733-c86aee2c-3bff-4b78-be54-003823d60276.png)

更易于滚动的剧集列表，有保持紧凑列表或将其变为网格菜单的选项。

```css
@import url('https://cdn.jsdelivr.net/gh/CTalvio/Ultrachromic/episodelist/episodes_compactlist.css');
```
或者
```css
@import url('https://cdn.jsdelivr.net/gh/CTalvio/Ultrachromic/episodelist/episodes_grid.css');
```

<br />

### 6. 透明顶部栏

![image](https://user-images.githubusercontent.com/4365015/127768778-056a68eb-402f-49d0-8277-c11a71edbbe5.png)

透明顶部栏。

```css
@import url('https://cdn.jsdelivr.net/gh/CTalvio/Ultrachromic/header/header_transparent.css');
```

<br />

### 7. 登录界面

![image](https://user-images.githubusercontent.com/4365015/127768970-e827c7e4-f4ce-4229-a68a-b2e87a723ef0.png)

登录界面样式。极简主义选项没有边框或提示文字。你还可以设置自定义背景，见下文。

```css
@import url('https://cdn.jsdelivr.net/gh/CTalvio/Ultrachromic/login/login_minimalistic.css');
```
或者
```css
@import url('https://cdn.jsdelivr.net/gh/CTalvio/Ultrachromic/login/login_frame.css');
```

<br />

### 8. 输入框

![image](https://user-images.githubusercontent.com/4365015/127769216-1d04cd30-14e0-4fda-9b2c-e0bfdb3514f6.png)

输入框样式，具有选中时突出显示的边框，或无边框，以及选中时背景高亮。

```css
@import url('https://cdn.jsdelivr.net/gh/CTalvio/Ultrachromic/fields/fields_border.css');
```
或者
```css
@import url('https://cdn.jsdelivr.net/gh/CTalvio/Ultrachromic/fields/fields_noborder.css');
```

<br />

### 9. 观看/未观看指示器

![image](https://user-images.githubusercontent.com/4365015/127769354-f7a0c402-0c9a-4a8e-a347-e6c352ecabbf.png)

两种选项，指示器浮动还是附加到标题卡片的角落。

```css
@import url('https://cdn.jsdelivr.net/gh/CTalvio/Ultrachromic/cornerindicator/indicator_floating.css');
```
或者
```css
@import url('https://cdn.jsdelivr.net/gh/CTalvio/Ultrachromic/cornerindicator/indicator_corner.css');
```

<br />

### 10. 类型选择

![Untitled](https://user-images.githubusercontent.com/4365015/127774204-03957527-7178-4ea2-8674-d83fe6a97d1c.png)

深色、浅色和多彩类型。你必须选用其中之一。如果你想在深色模式下使用强调色，请使用带有"_withaccent"的行。

```css
@import url('https://cdn.jsdelivr.net/gh/CTalvio/Ultrachromic/type/dark.css');
```
或者
```css
@import url('https://cdn.jsdelivr.net/gh/CTalvio/Ultrachromic/type/light.css');
```
或者
```css
@import url('https://cdn.jsdelivr.net/gh/CTalvio/Ultrachromic/type/colorful.css');
```
或者
```css
@import url('https://cdn.jsdelivr.net/gh/CTalvio/Ultrachromic/type/dark_withaccent.css');
```

<br />

### 11. 封面详情页

![image](https://user-images.githubusercontent.com/4365015/127778994-ddee8235-6bb2-42ae-a8b1-f9023dc69398.png)


提供四种样式选择，每种都有带logo和不带logo两个版本。
```css
@import url('https://cdn.jsdelivr.net/gh/CTalvio/Ultrachromic/titlepage/title_simple.css');
```
或者
```css
@import url('https://cdn.jsdelivr.net/gh/CTalvio/Ultrachromic/titlepage/title_simple-logo.css');
```
或者
```css
@import url('https://cdn.jsdelivr.net/gh/CTalvio/Ultrachromic/titlepage/title_banner.css');
```
或者
```css
@import url('https://cdn.jsdelivr.net/gh/CTalvio/Ultrachromic/titlepage/title_banner-logo.css');
```

<br />

### 12. 已观看进度条

![Screenshot_20210817_003507](https://user-images.githubusercontent.com/4365015/129632467-b545bcfc-3dbe-430d-8d3c-e89355eae29e.png)

针对观看进度记录提供的默认、覆盖或浮动式进度指示器。

```css
@import url('https://cdn.jsdelivr.net/gh/CTalvio/Ultrachromic/overlayprogress.css');
```
或者
```css
@import url('https://cdn.jsdelivr.net/gh/CTalvio/Ultrachromic/bottombarprogress.css');
```
或者
```css
@import url('https://cdn.jsdelivr.net/gh/CTalvio/Ultrachromic/progress/floating.css');
```

<br />

### 13. 动画效果（可多选）

![image](https://user-images.githubusercontent.com/4365015/127781073-c2a2a1f1-4c60-4c57-afa9-13a4775489bb.png)

额外的视觉美化功能。鼠标悬停时让元素发光，使某些界面元素呈现透明玻璃质感。平移动画以缓慢的移动方式动态展示背景。最后一个选项是一种在移动设备上将封面上变为背景的快捷方法，因为此功能在10.7.0中被移除。

已知问题：当背景也修改时，平移动画可能导致基于Chromium的浏览器闪烁。

```css
@import url('https://cdn.jsdelivr.net/gh/CTalvio/Ultrachromic/effects/hoverglow.css');
```
或者/和
```css
@import url('https://cdn.jsdelivr.net/gh/CTalvio/Ultrachromic/effects/glassy.css');
```
或者/和
```css
@import url('https://cdn.jsdelivr.net/gh/CTalvio/Ultrachromic/effects/pan-animation.css');
```
或者/和
```css
@import url('https://ctalvio.github.io/Monochromic/backdrop-hack_style.css');
```

<br />

### 14. 手动配置

如有需要，您可以在导入行之后添加以下简短代码片段，可以编辑它来设置登录背景，调整背景模糊程度，以及自定义强调色。

```css
/*Style backdrop*/
.backdropImage {filter: blur(18px) saturate(120%) contrast(120%) brightness(40%);}

/*Login background*/
#loginPage {background: url(https://i.imgur.com/9vL4iNf.png) !important;}

/*Accent and roundingd*/
:root {--accent: 98, 121, 205;}
:root {--rounding: 12px;}
```

<br />

### 额外资源

[查看 @prayag17 制作的自定义图标！](https://github.com/prayag17/Jellyfin-Icons)

还要特别感谢 prayag17，我在这个项目中加入了他的部分代码。（网格剧集、标题logo）

<br />
<br />

### Fix for use with some reverse proxy setups

使用来自 [Jellyfin docs](https://jellyfin.org/docs/general/networking/nginx.html) 的Nginx反向代理配置时，默认情况下主题无法正常工作。（如果您使用的是子路径配置，可忽略此部分）

由于配置包含Content-Security-Policy以降低XSS风险，因此需要将本仓库中的URL和字体添加到允许的外部源列表中。

在nginx配置文件中，应将

```
add_header Content-Security-Policy ....
```
改为

```
add_header Content-Security-Policy "default-src https: data: blob:; style-src 'self' 'unsafe-inline' https://cdn.jsdelivr.net/gh/CTalvio/Ultrachromic/accentlist.css https://cdn.jsdelivr.net/gh/CTalvio/Ultrachromic/base.css https://cdn.jsdelivr.net/gh/CTalvio/Ultrachromic/bottombarprogress.css https://cdn.jsdelivr.net/gh/CTalvio/Ultrachromic/fixes.css https://cdn.jsdelivr.net/gh/CTalvio/Ultrachromic/jf_font.css https://cdn.jsdelivr.net/gh/CTalvio/Ultrachromic/overlayprogress.css https://cdn.jsdelivr.net/gh/CTalvio/Ultrachromic/rounding.css https://cdn.jsdelivr.net/gh/CTalvio/Ultrachromic/rounding_circlehover.css https://cdn.jsdelivr.net/gh/CTalvio/Ultrachromic/smallercast.css https://cdn.jsdelivr.net/gh/CTalvio/Ultrachromic/rounding_circlehover.css https://cdn.jsdelivr.net/gh/CTalvio/Ultrachromic/cornerindicator/indicator_floating.css https://cdn.jsdelivr.net/gh/CTalvio/Ultrachromic/cornerindicator/indicator_corner.css https://cdn.jsdelivr.net/gh/CTalvio/Ultrachromic/effects/glassy.css https://cdn.jsdelivr.net/gh/CTalvio/Ultrachromic/effects/pan-animation.css https://ctalvio.github.io/Monochromic/backdrop-hack_style.css https://cdn.jsdelivr.net/gh/CTalvio/Ultrachromic/effects/hoverglow.css https://cdn.jsdelivr.net/gh/CTalvio/Ultrachromic/effects/scrollfade.css https://cdn.jsdelivr.net/gh/CTalvio/Ultrachromic/episodelist/episodes_compactlist.css https://cdn.jsdelivr.net/gh/CTalvio/Ultrachromic/episodelist/episodes_grid.css https://cdn.jsdelivr.net/gh/CTalvio/Ultrachromic/fields/fields_border.css https://cdn.jsdelivr.net/gh/CTalvio/Ultrachromic/fields/fields_noborder.css https://cdn.jsdelivr.net/gh/CTalvio/Ultrachromic/header/header_transparent.css https://cdn.jsdelivr.net/gh/CTalvio/Ultrachromic/header/header_transparent-dashboard.css https://cdn.jsdelivr.net/gh/CTalvio/Ultrachromic/login/login_frame.css https://cdn.jsdelivr.net/gh/CTalvio/Ultrachromic/login/login_minimalistic.css https://cdn.jsdelivr.net/gh/CTalvio/Ultrachromic/login/login_frame.css https://cdn.jsdelivr.net/gh/CTalvio/Ultrachromic/presets/monochromic_preset.css https://cdn.jsdelivr.net/gh/CTalvio/Ultrachromic/presets/kaleidochromic_preset.css https://cdn.jsdelivr.net/gh/CTalvio/Ultrachromic/presets/novachromic_preset.css https://cdn.jsdelivr.net/gh/CTalvio/Ultrachromic/titlepage/title_banner.css https://cdn.jsdelivr.net/gh/CTalvio/Ultrachromic/titlepage/title_banner-logo.css https://cdn.jsdelivr.net/gh/CTalvio/Ultrachromic/titlepage/title_simple.css https://cdn.jsdelivr.net/gh/CTalvio/Ultrachromic/titlepage/title_simple-logo.css https://cdn.jsdelivr.net/gh/CTalvio/Ultrachromic/type/light.css https://cdn.jsdelivr.net/gh/CTalvio/Ultrachromic/type/dark.css https://cdn.jsdelivr.net/gh/CTalvio/Ultrachromic/type/colorful.css https://cdn.jsdelivr.net/gh/CTalvio/Ultrachromic/type/dark_withaccent.css https://fonts.googleapis.com/css2; script-src 'self' 'unsafe-inline' https://www.gstatic.com/cv/js/sender/v1/cast_sender.js worker-src 'self' blob:; connect-src 'self'; object-src 'none'; frame-ancestors 'self'";
```

如果不这样做，主题将不会加载（恢复为默认主题），浏览器控制台会显示错误。即使您复制了所有CSS，由于字体是从外部源加载的，仍然无法加载。
