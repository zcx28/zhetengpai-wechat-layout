# 红白简洁组件

基于 `isjiamu/gzh-design-skill` 的红白主题调整，许可见 [../LICENSE](../LICENSE)。以下槽位由实际文章替换；交付前删除空区块与全部未填槽位。

## 全局容器

按“引言与前言 → 章节 → END → 简介图与普通字重互动语”的顺序填入。

```html
<section style="max-width:677px;margin:0 auto;background:#ffffff;font-family:-apple-system,BlinkMacSystemFont,'PingFang SC','Hiragino Sans GB','Microsoft YaHei',sans-serif;color:#374151;line-height:1.75;letter-spacing:0.5px;overflow-x:hidden;">
  {{正文组件}}
</section>
```

## 开头引言

整段统一字重，不在词组上添加另一层色块。没有适合放这里的原文段落时省略。

```html
<section style="margin:10px 10px 32px;background:#ffffff;border-radius:12px;box-shadow:0 4px 24px -4px rgba(220,38,38,0.15);padding:28px 24px 22px;overflow:hidden;">
  <p style="font-size:42px;color:#DC2626;font-weight:900;margin:0;line-height:0.6;"><span leaf="">“</span></p>
  <p style="font-size:16px;font-weight:800;color:#1C1917;margin:12px 0 8px;line-height:1.75;padding-left:4px;"><span leaf="">{{原文开头段落}}</span></p>
</section>
```

## 普通正文与完整句强调

前言段落包在 `<section style="padding:0 10px;">` 中；章内段落直接放入章节容器。正文默认一整段一个 leaf；只在选中的完整句外添加 strong。

```html
<p style="margin:0 0 20px;font-size:15px;line-height:1.8;text-align:justify;"><span leaf="">{{普通段落}}</span></p>

<p style="margin:0 0 20px;font-size:15px;line-height:1.8;text-align:justify;"><strong><span leaf="">{{完整的重点句，含句末标点。}}</span></strong></p>
```

长段中只有一句需要突出时，使用下面的结构；这三段文字必须来自原文，不改句序。

```html
<p style="margin:0 0 20px;font-size:15px;line-height:1.8;text-align:justify;"><span leaf="">{{前文}}</span><strong><span leaf="">{{完整重点句。}}</span></strong><span leaf="">{{后文}}</span></p>
```

## 章节标题

首章 `margin-top:16px`，后续章节 `48px`。英文标签可选；没有时删除其整个 p。这里没有章节底线，不另加分割线。

```html
<section style="margin-top:48px;margin-bottom:28px;padding:0 10px;">
  <section style="display:flex;align-items:center;margin-bottom:20px;padding-bottom:14px;">
    <span style="display:inline-block;background:#DC2626;color:#FFFFFF;font-size:18px;font-weight:900;padding:4px 14px;border-radius:6px;margin-right:14px;line-height:1.3;"><span leaf="">{{01}}</span></span>
    <section>
      <p style="font-size:10px;color:#DC2626;font-weight:700;letter-spacing:3px;margin:0 0 2px;"><span leaf="">{{已有英文标签}}</span></p>
      <h3 style="font-size:18px;font-weight:800;color:#1C1917;margin:0;letter-spacing:0.5px;"><span leaf="">{{章节标题}}</span></h3>
    </section>
  </section>
  {{本章段落}}
</section>
```

## 小节标题

```html
<p style="font-size:15px;font-weight:800;color:#1C1917;margin:28px 0 14px;padding-left:10px;border-left:3px solid #DC2626;line-height:1.4;"><span leaf="">{{小节标题}}</span></p>
```

## 列表

每项复制一次，数字替换为实际序号。列表正文保持普通字重。

```html
<section style="display:flex;align-items:flex-start;margin-bottom:12px;">
  <span style="display:inline-flex;align-items:center;justify-content:center;width:22px;height:22px;background:#DC2626;color:#fff;font-size:12px;font-weight:700;border-radius:50%;flex-shrink:0;margin:2px 10px 0 0;"><span leaf="">{{1}}</span></span>
  <p style="font-size:15px;color:#374151;margin:0;line-height:1.8;flex:1;"><span leaf="">{{列表项原文}}</span></p>
</section>
```

## 正文图片

真实图片说明存在时才额外添加居中的说明段落。原图按比例显示，不裁切、不放大小图。

```html
<section style="margin:0 0 20px;text-align:center;"><span leaf=""><img src="{{真实图片地址或内嵌图片数据}}" alt="{{已有图片说明，无则空}}" style="max-width:100%;height:auto;display:block;margin:0 auto;"></span></section>
```

## END 与作者简介

END 后使用真实名片原图，没有原图就删除整个图片区块。CTA 为普通字重完整段落，不能把“点赞、在看、转发”单独加粗。

```html
<section style="padding:0 10px;">
  <p style="text-align:center;margin:0 0 32px;font-size:11px;color:#DC2626;letter-spacing:3px;"><span leaf="">END</span></p>
</section>
<section style="padding:0 10px;">
  <section style="text-align:center;margin-bottom:10px;border-radius:12px;overflow:hidden;"><span leaf=""><img src="{{真实名片图片地址或内嵌图片数据}}" alt="折腾派简介" style="max-width:100%;height:auto;display:block;margin:0 auto;"></span></section>
  <p style="margin:0 0 20px;font-size:15px;line-height:1.8;text-align:justify;"><span leaf="">如果你觉得今天这篇有收获，欢迎点赞、在看、转发三连，我们下篇见。</span></p>
</section>
```
