---
layout: post
category: "HTML"
title:  "Html input=file指定文件类型"
tags: [HTML]
---

For Excel Files 2003-2007 (.xls), use:

```html
<!--
.doc => application/msword
.dot => application/msword
.xls => application/vnd.ms-excel
.ppt => application/vnd.ms-powerpoint
-->
<input type="file" accept="application/vnd.ms-excel" />
```

For Excel Files 2010 (.xlsx), use:

```html
<!--
    .dotx => application/vnd.openxmlformats-officedocument.wordprocessingml.template
    .docx => application/vnd.openxmlformats-officedocument.wordprocessingml.document
    .xlsx => application/vnd.openxmlformats-officedocument.spreadsheetml.sheet
    .pptx => application/vnd.openxmlformats-officedocument.presentationml.presentation
-->
<input type="file" accept="application/vnd.openxmlformats-officedocument.spreadsheetml.sheet" />
```

For CSV files (.csv), use:

```html
<input type="file" accept=".csv" />
```

For Text Files (.txt) use:

```html
<input type="file" accept="text/plain" />
```

For Image Files (.png/.jpg/etc), use:

```html
<input type="file" accept="image/*" />
```

For HTML Files (.htm,.html), use:

```html
<input type="file" accept="text/html" />
```

For Video Files (.avi, .mpg, .mpeg, .mp4), use:

```html
<input type="file" accept="video/*" />
```

For Audio Files (.mp3, .wav, etc), use:

```html
<input type="file" accept="audio/*" />
```

For PDF Files, use:

```html
<input type="file" accept=".pdf" />
```

## Note:

多个时，accept 值使用`逗号`隔开。
