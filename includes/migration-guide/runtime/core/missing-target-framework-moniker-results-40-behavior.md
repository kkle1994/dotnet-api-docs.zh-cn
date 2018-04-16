### <a name="missing-target-framework-moniker-results-in-40-behavior"></a><span data-ttu-id="ff9cd-101">缺少目标框架名字对象会导致 4.0 行为</span><span class="sxs-lookup"><span data-stu-id="ff9cd-101">Missing Target Framework Moniker results in 4.0 behavior</span></span>

|   |   |
|---|---|
|<span data-ttu-id="ff9cd-102">详细信息</span><span class="sxs-lookup"><span data-stu-id="ff9cd-102">Details</span></span>|<span data-ttu-id="ff9cd-103">没有应用程序<xref:System.Runtime.Versioning.TargetFrameworkAttribute?displayProperty=name>在使用.NET Framework 4.0 的语义 (quirks) 自动运行该程序集级别将应用。</span><span class="sxs-lookup"><span data-stu-id="ff9cd-103">Applications without a <xref:System.Runtime.Versioning.TargetFrameworkAttribute?displayProperty=name> applied at the assembly level will automatically run using the semantics (quirks) of the .NET Framework 4.0.</span></span> <span data-ttu-id="ff9cd-104">若要确保高质量，建议所有二进制文件显式均归因与<xref:System.Runtime.Versioning.TargetFrameworkAttribute?displayProperty=name>表示它们生成所用的.NET framework 的版本。</span><span class="sxs-lookup"><span data-stu-id="ff9cd-104">To ensure high quality, it is recommended that all binaries be explicitly attributed with a <xref:System.Runtime.Versioning.TargetFrameworkAttribute?displayProperty=name> indicating the version of the .NET Framework they were built with.</span></span> <span data-ttu-id="ff9cd-105">请注意，在项目文件中使用的目标框架名字对象将导致 MSBuild 自动应用<xref:System.Runtime.Versioning.TargetFrameworkAttribute?displayProperty=name>。</span><span class="sxs-lookup"><span data-stu-id="ff9cd-105">Note that using a target framework moniker in a project file will cause MSBuild to automatically apply a <xref:System.Runtime.Versioning.TargetFrameworkAttribute?displayProperty=name>.</span></span>|
|<span data-ttu-id="ff9cd-106">建议</span><span class="sxs-lookup"><span data-stu-id="ff9cd-106">Suggestion</span></span>|<span data-ttu-id="ff9cd-107">A<xref:System.Runtime.Versioning.TargetFrameworkAttribute?displayProperty=name>应提供，通过将特性添加到程序集的直接或通过指定中的目标框架[项目文件或通过 Visual Studio 项目属性 GUI](http://blogs.msdn.com/b/visualstudio/archive/2010/05/19/visual-studio- managed-multi-targeting-part-1-concepts-target-framework-moniker-target-framework.aspx)。</span><span class="sxs-lookup"><span data-stu-id="ff9cd-107">A <xref:System.Runtime.Versioning.TargetFrameworkAttribute?displayProperty=name> should be supplied, either through adding the attribute directly to the assembly or by specifying a target framework in the [project file or through Visual Studio's project properties GUI](http://blogs.msdn.com/b/visualstudio/archive/2010/05/19/visual-studio- managed-multi-targeting-part-1-concepts-target-framework-moniker-target-framework.aspx).</span></span>|
|<span data-ttu-id="ff9cd-108">范围</span><span class="sxs-lookup"><span data-stu-id="ff9cd-108">Scope</span></span>|<span data-ttu-id="ff9cd-109">主要</span><span class="sxs-lookup"><span data-stu-id="ff9cd-109">Major</span></span>|
|<span data-ttu-id="ff9cd-110">版本</span><span class="sxs-lookup"><span data-stu-id="ff9cd-110">Version</span></span>|<span data-ttu-id="ff9cd-111">4.5</span><span class="sxs-lookup"><span data-stu-id="ff9cd-111">4.5</span></span>|
|<span data-ttu-id="ff9cd-112">类型</span><span class="sxs-lookup"><span data-stu-id="ff9cd-112">Type</span></span>|<span data-ttu-id="ff9cd-113">运行时</span><span class="sxs-lookup"><span data-stu-id="ff9cd-113">Runtime</span></span>|
