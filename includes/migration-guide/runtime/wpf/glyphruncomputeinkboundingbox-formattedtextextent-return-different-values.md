### <a name="glyphruncomputeinkboundingbox-and-formattedtextextent-return-different-values-beginning-in-net-45"></a><span data-ttu-id="e91d5-101">GlyphRun.ComputeInkBoundingBox() 和 FormattedText.Extent 返回不同的值从.NET 4.5 开始</span><span class="sxs-lookup"><span data-stu-id="e91d5-101">GlyphRun.ComputeInkBoundingBox() and FormattedText.Extent return different values beginning in .NET 4.5</span></span>

|   |   |
|---|---|
|<span data-ttu-id="e91d5-102">详细信息</span><span class="sxs-lookup"><span data-stu-id="e91d5-102">Details</span></span>|<span data-ttu-id="e91d5-103">对已进行了改进<xref:System.Windows.Media.GlyphRun.ComputeInkBoundingBox>和<xref:System.Windows.Media.FormattedText.Extent>在.NET Framework 4.5 来解决问题框已太小，在某些情况下，.NET Framework 4.0 中包含的标志符号。</span><span class="sxs-lookup"><span data-stu-id="e91d5-103">Improvements were made to <xref:System.Windows.Media.GlyphRun.ComputeInkBoundingBox> and <xref:System.Windows.Media.FormattedText.Extent> in the .NET Framework 4.5 to address issues where the boxes were too small for the contained glyphs in some cases in the .NET Framework 4.0.</span></span> <span data-ttu-id="e91d5-104">因此，从 .NET Framework 4.5 开始，某些范围框将更大，从而使 UI 布局产生细微差异。</span><span class="sxs-lookup"><span data-stu-id="e91d5-104">As a result of this, some bounding boxes will be larger beginning in the .NET Framework 4.5, resulting in subtle differences in UI layout.</span></span>|
|<span data-ttu-id="e91d5-105">建议</span><span class="sxs-lookup"><span data-stu-id="e91d5-105">Suggestion</span></span>|<span data-ttu-id="e91d5-106">请注意，某些字形范围框大小已增加。</span><span class="sxs-lookup"><span data-stu-id="e91d5-106">Be aware that some glyph bounding box sizes have increased.</span></span> <span data-ttu-id="e91d5-107">这些更改通常会改进展示和点击框测试，但如果需要使用旧（.NET 4.5 之前的）行为，可通过以下条目添加到 app.config 文件进行选择：</span><span class="sxs-lookup"><span data-stu-id="e91d5-107">These changes will usually improve presentation and hit box testing, but if the older (pre-.NET 4.5) behavior is desired, it can be opted into by adding the following entry to the app.config file:</span></span><pre><code class="language-xml">&lt;appsettings&gt;&#13;&#10;&lt;add key=&quot;IncludeAllInkInBoundingBox&quot; value=&quot;false&quot;&gt;&#13;&#10;&lt;/appsettings&gt;&#13;&#10;</code></pre>|
|<span data-ttu-id="e91d5-108">范围</span><span class="sxs-lookup"><span data-stu-id="e91d5-108">Scope</span></span>|<span data-ttu-id="e91d5-109">边缘</span><span class="sxs-lookup"><span data-stu-id="e91d5-109">Edge</span></span>|
|<span data-ttu-id="e91d5-110">版本</span><span class="sxs-lookup"><span data-stu-id="e91d5-110">Version</span></span>|<span data-ttu-id="e91d5-111">4.5</span><span class="sxs-lookup"><span data-stu-id="e91d5-111">4.5</span></span>|
|<span data-ttu-id="e91d5-112">类型</span><span class="sxs-lookup"><span data-stu-id="e91d5-112">Type</span></span>|<span data-ttu-id="e91d5-113">运行时</span><span class="sxs-lookup"><span data-stu-id="e91d5-113">Runtime</span></span>|
|<span data-ttu-id="e91d5-114">受影响的 API</span><span class="sxs-lookup"><span data-stu-id="e91d5-114">Affected APIs</span></span>|<ul><li><xref:System.Windows.Media.GlyphRun.ComputeInkBoundingBox?displayProperty=nameWithType></li><li><xref:System.Windows.Media.FormattedText.Extent?displayProperty=nameWithType></li></ul>|
