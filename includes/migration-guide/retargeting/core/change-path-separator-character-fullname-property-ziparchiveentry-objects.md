### <a name="change-in-path-separator-character-in-fullname-property-of-ziparchiveentry-objects"></a><span data-ttu-id="c184f-101">更改路径分隔符字符，在 ZipArchiveEntry 对象 FullName 属性</span><span class="sxs-lookup"><span data-stu-id="c184f-101">Change in path separator character in FullName property of ZipArchiveEntry objects</span></span>

|   |   |
|---|---|
|<span data-ttu-id="c184f-102">详细信息</span><span class="sxs-lookup"><span data-stu-id="c184f-102">Details</span></span>|<span data-ttu-id="c184f-103">对于面向.NET Framework 4.6.1 及更高版本的应用程序，路径分隔符字符已从反斜杠 (&quot;&quot;) 为正斜杠 (&quot;/&quot;) 中<xref:System.IO.Compression.ZipArchiveEntry.FullName>属性<xref:System.IO.Compression.ZipArchiveEntry>的重载创建的对象<xref:System.IO.Compression.ZipFile.CreateFromDirectory%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="c184f-103">For apps that target the .NET Framework 4.6.1 and later versions, the path separator character has changed from a backslash (&quot;&quot;) to a forward slash (&quot;/&quot;) in the <xref:System.IO.Compression.ZipArchiveEntry.FullName> property of <xref:System.IO.Compression.ZipArchiveEntry>  objects created by overloads of the <xref:System.IO.Compression.ZipFile.CreateFromDirectory%2A> method.</span></span> <span data-ttu-id="c184f-104">更改为带来了到与 4.4.17.1 一部分的符合性的.NET 实现[。ZIP 文件格式规格](https://pkware.cachefly.net/webdocs/casestudies/APPNOTE.TXT)，并允许。ZIP 存档解压缩在非 Windows 系统上。解压缩 zip 文件由应用创建的针对以前版本的.NET framework 在非 Windows 操作系统，例如 Macintosh 上无法保留目录结构。</span><span class="sxs-lookup"><span data-stu-id="c184f-104">The change brings the .NET implementation into conformity with section 4.4.17.1 of the [.ZIP File Format Specification](https://pkware.cachefly.net/webdocs/casestudies/APPNOTE.TXT) and allows .ZIP archives to be decompressed on non-Windows systems.Decompressing a zip file created by an app that targets a previous version of the .NET Framework on non-Windows operating systems such as the Macintosh fails to preserve the directory structure.</span></span> <span data-ttu-id="c184f-105">例如，在该系统中，它创建一组文件，其文件名连接的目录路径，以及任何反斜杠 (&quot;&quot;) 字符，以及的文件名。</span><span class="sxs-lookup"><span data-stu-id="c184f-105">For example, on the Macintosh, it creates a set of files whose filename concatenates the directory path, along with any backslash (&quot;&quot;) characters, and the filename.</span></span> <span data-ttu-id="c184f-106">因此，不会保留解压缩的文件的目录结构。</span><span class="sxs-lookup"><span data-stu-id="c184f-106">As a result, the directory structure of decompressed files is not preserved.</span></span>|
|<span data-ttu-id="c184f-107">建议</span><span class="sxs-lookup"><span data-stu-id="c184f-107">Suggestion</span></span>|<span data-ttu-id="c184f-108">在此更改的影响。在 Windows 操作系统解压缩由.NET Framework 中的 Api 的 ZIP 文件<xref:System.IO?displayProperty=nameWithType>命名空间应是最小，因为这些 Api 可以无缝地处理任一斜杠 (&quot;/&quot;) 或反斜杠 (&quot;\&q u o t;) 作为路径分隔符字符。如果此更改是不可取的则可以通过添加配置设置为选择退出[\<运行时 >](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md)的应用程序配置文件的部分。</span><span class="sxs-lookup"><span data-stu-id="c184f-108">The impact of this change on .ZIP files that are decompressed on the Windows operating system by APIs in the .NET Framework <xref:System.IO?displayProperty=nameWithType> namespace should be minimal, since these APIs can seamlessly handle either a slash (&quot;/&quot;) or a backslash (&quot;\&quot;) as the path separator character.If this change is undesirable, you can opt out of it by adding a configuration setting to the [\<runtime>](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md) section of your application configuration file.</span></span> <span data-ttu-id="c184f-109">下面的示例演示`<runtime>`部分和`Switch.System.IO.Compression.ZipFile.UseBackslash`选择退出交换机：</span><span class="sxs-lookup"><span data-stu-id="c184f-109">The following example shows both the `<runtime>` section and the `Switch.System.IO.Compression.ZipFile.UseBackslash` opt-out switch:</span></span><pre><code class="language-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.IO.Compression.ZipFile.UseBackslash=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre><span data-ttu-id="c184f-110">此外，面向以前版本的.NET Framework 但在.NET Framework 4.6.1 及更高版本上运行的应用可以选择加入此行为通过将添加到某一配置设置[\<运行时 >](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md)应用程序配置文件节。</span><span class="sxs-lookup"><span data-stu-id="c184f-110">In addition, apps that target previous versions of the .NET Framework but are running on the .NET Framework 4.6.1 and later versions can opt in to this behavior by adding a configuration setting to the [\<runtime>](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md) section of the application configuration file.</span></span> <span data-ttu-id="c184f-111">下面的示例演示同时`<runtime>`部分和`Switch.System.IO.Compression.ZipFile.UseBackslash`参加交换机。</span><span class="sxs-lookup"><span data-stu-id="c184f-111">The following shows both the `<runtime>` section and the `Switch.System.IO.Compression.ZipFile.UseBackslash` opt-in switch.</span></span><pre><code class="language-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.IO.Compression.ZipFile.UseBackslash=false&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>|
|<span data-ttu-id="c184f-112">范围</span><span class="sxs-lookup"><span data-stu-id="c184f-112">Scope</span></span>|<span data-ttu-id="c184f-113">边缘</span><span class="sxs-lookup"><span data-stu-id="c184f-113">Edge</span></span>|
|<span data-ttu-id="c184f-114">版本</span><span class="sxs-lookup"><span data-stu-id="c184f-114">Version</span></span>|<span data-ttu-id="c184f-115">4.6.1</span><span class="sxs-lookup"><span data-stu-id="c184f-115">4.6.1</span></span>|
|<span data-ttu-id="c184f-116">类型</span><span class="sxs-lookup"><span data-stu-id="c184f-116">Type</span></span>|<span data-ttu-id="c184f-117">重定目标</span><span class="sxs-lookup"><span data-stu-id="c184f-117">Retargeting</span></span>|
|<span data-ttu-id="c184f-118">受影响的 API</span><span class="sxs-lookup"><span data-stu-id="c184f-118">Affected APIs</span></span>|<ul><li><xref:System.IO.Compression.ZipFile.CreateFromDirectory(System.String,System.String)?displayProperty=nameWithType></li><li><xref:System.IO.Compression.ZipFile.CreateFromDirectory(System.String,System.String,System.IO.Compression.CompressionLevel,System.Boolean)?displayProperty=nameWithType></li><li><xref:System.IO.Compression.ZipFile.CreateFromDirectory(System.String,System.String,System.IO.Compression.CompressionLevel,System.Boolean,System.Text.Encoding)?displayProperty=nameWithType></li></ul>|
