(z2b)=
# 零到Binder

在本章中，我们将从零开始创建一个Binder项目：我们将首先在GitHub 上创建一个仓库，然后在mybinder.org上启动。 您要完成任务的部分由三个流量光线表示：vertical_traffic_light：emojis。 一些步骤给予您Python、Julia或R选项 - 点击您首选语言的选项卡。

```{admonition} Attributions
本教程基于Tim Head的_Zero-to-Binder_工作坊，可以在这里找到： <http://bit.ly/zero-to-binder> 和 <http://bit.ly/zero-to-binder-rise>

感谢您Anna Krystalli 和 Oliver Strickson帮助开发R和Julia 内容。
```

```{attention}
Binder可能需要很长时间才能加载，但这并不一定意味着您的绑定将无法启动。
如果您看到“……加载时间较长，挂载时间！” 消息，您总是可以刷新窗口。
```

```{admonition} If you are using R...
如果你正在沿着R之路，我们已经包含了一些替代步骤使用 [`holepunch` 包](https://github)。 这将使用 [rocker base image](https://github.com/rocker-org/rocker)构建您的环境，最终应该更快地构建和启动您的环境。
```

(z2b-reqs)=
## B. 所需经费

您将需要：

- **一些代码和一些数据。 ** 代码运行需要小于 **10分钟的**和数据应小于 **10 MB** 这可能意味着您只从一个更大的项目中选择一个脚本，或者带上一个数据的子集。 Note that it's really important that the code and data can be made **public** because we'll be using the public binder instance.
- **GitHub 帐户。 ** 如果您还没有一个，请注册一个账户： <https://github.com/join>

(z2b-step-1)=
## 1. 1. 创建一个绑定的repo

🚦🚦🚦

````{tabbed} Python
1) 在 GitHub 上创建一个名为“my-first binder”
   - 请确保仓库是 **public**, _不是私有!
   - 不要忘记用README初始化仓库！
   - 不要忘记用README初始化仓库！
2) 通过第一行上的 `print("Hello.py" 创建一个名为 `hello.py" 的文件，并提交到 `main` 分支
````

````{tabbed} Julia
1) 在 GitHub 上创建一个名为“my-first binder”
   - 请确保仓库是 **public**, _不是私有!
   - 不要忘记用README初始化仓库！
   - 不要忘记用README初始化仓库！
2) 创建一个名为 `hello' 的文件。 l`通过 `println("Hello from Binder! )在第一行上提交到 `main` 分支
3。 创建一个名为 `Project' 的文件。 oml`(警告: 资本化很重要!) 带有以下内容并将其提交到 "main"。
   这将把Julia安装到Binder环境中。

   ```julia
   [compat]
   julia = "1.3"
```
````

````{tabbed} R
1) 在 GitHub 上创建一个名为“my-first binder”
   - 请确保仓库是 **public**, _不是私有!
   - 不要忘记用README初始化仓库！
   - 不要忘记用README初始化仓库！
2) 创建一个名为 `hello' 的文件。 通过 `print("Hello from Binder! )在第一行上提交到 `main` 分支
3。 创建一个名为 `runtime 的文件。 第一行使用 `r-2022-01-01`。
   这个日期代表我们将使用的 [CRAN](https://cran.r-project.org/) [RStudio 软件包管理器](https://packemanager.rstudio.com)的快照。
   提交此文件到 "main" 分支。

   ``{note}
   在R 中你可以使用 `holepunch::write_runtime()` 在`.binder/` 目录下创建 `runtime.txt`; 它将与今天的日期配置。
   ```
````
(z2b-public repo)=
### 为什么要公开？
mybinder.org无法访问私有仓库，因为这需要一个秘密令牌。 Binder团队选择不承担处理秘密令牌的责任，因为mybinder.org是一种公共服务，是技术概念的证明。 如果访问私有仓库是您/您的团队需要的功能，我们建议您研究如何建立您自己的 [BinderHub](https://binderhub.readthedocs.io)。
(z2b-8步)=
## 2. 2. 启动你的第一个仓库！
🚦🚦🚦
🚦🚦🚦 1) 转到 **<https://mybinder.org>** (2) 将您的 repo 的 URL 输入到"GitHub repo 或 URL" 框中。 看起来像这样：
> **https://github.com/YOUR-USERNAME/my-first binder** 3) 当您键入时，网页将生成一个链接到“复制下面的URL”。 ." 框 它看起来像这样： **https://mybinder。 rg/v2/gh/YOUR-USERNAME/my-first binder/HEAD** 4) 复制它， 打开一个新的浏览器标签页并访问URL - 当Binder启动repo 时，你会看到一个“旋转器” 如果一切顺利，你会看到JupyterLab 接口。
如果一切顺利，你会看到JupyterLab 接口。
(z2b-4)=
### 背景情况如何？ - 第1部分
开始很容易，但我们的环境是野蛮的 - 让我们添加一个 **依赖关系**！
- 分享 **https://mybinder.org/v2/gh/YOUR-USERNAME/my-first binder/HEAD** URL
- 分析内容
- 等候时，绑定Hub (绑定器的后端)： - 从 GitHub 获取你的repo - 分析内容 - 基于你的仓库构建停靠图像 - 在云端启动 Docker 图像 - 通过您的浏览器连接您的 (z2b-step-3)=
- 在云端启动 Docker 图像
- 通过您的浏览器连接您的
(z2b-5步)=
## 3. 3. 运行脚本
🚦🚦🚦

````{tabbed} Python
1. 1. 从启动面板中选择“终端”
2。 在新的终端窗口中，输入 `python hello.py` 然后按返回
````

````{tabbed} Julia
1. 1. 从启动面板中选择“终端”
2。 在新的终端窗口中，输入 `julia hello.jl` 并按返回
````

````{tabbed} R
1. 1. 从启动面板中选择“终端”
2。 在新的终端窗口中，输入 `Rscript -e 'source("hello.R")` 然后按返回
````

`你好来自绑定！ ` 应该打印到终端。

这一次，BinderHub 将读取您添加的配置文件并安装您请求的软件包的特定版本。
## 4. 固定依赖关系

(z2b-依赖)=

🚦🚦🚦

````{tabbed} Python
1) 在你的仓库中，创建一个名为 `requirements.txt`
2) 的文件，添加一行表示：`numpy==1.14.5`
3) 检查轮胎！ 然后提交到 `main` 分支
4) 访问**https://mybinder.org/v2/gh/YOUR-USERNAME/my-first binder/HEAD **
````

````{tabbed} Julia
1) 在你的仓库里编辑`项目。 oml` 文件
2) 添加一个新的块，表示：

   ```julia
   [deps]
   CSV = "336ed68f-0bac-5ca0-87d4-7b16caf5d00b"
   ```

3) 检查轮胎！ 然后承诺为“主”。
4) 在新标签页中再次访问 **https://mybinder.org/v2/gh/YOUR-USERNAME/my-first binder/HEAD **
````

````{tabbed} R
1) 在你的仓库中，创建一个名为 `install.R`
2) 的文件，添加一行表示：`install.packes("readr")`
3) 检查轮胎！ 然后提交到 `main` 分支
4) 访问 **https://mybinder。 rg/v2/gh/YOUR-USERNAME/my-first binder/HEAD** 在新标签

```{note}
如果使用 `holepunch` ，你可以创建一个 `install'。 文件并自动添加代码，通过`holepunch::write_install()`来安装项目中的所有依赖项。
```
````
这一次，点击大型、水平和灰色条形中的“构建日志”。 这将使您能够观看您的构建进度。 It's useful when your build fails or something you think _should_ be installed is missing.

```{note}
有时候绑定者的编译日志会以红色字体打印事物， 比如警告“pip”不是最新的 (`pip` 通常已经过时，因为它定期更新！ 或安装消息，特别是如果您正在使用 R. 的话。 这些红色消息不一定意味着你的构建出现问题，它将失败——仅仅是一个不幸的字体颜色选择！
```

(z2b-background-2)=
### 背景情况如何？ - 第二部分

Binder 全都是关于轻松分享您的工作，有两种方法可以做：

(z2b-大文件)=
### 更多关于固定依赖关系

````{tabbed} Python
在上述示例中，我们使用两个等效符号(`==`)来固定`numpy`的版本。
这会告诉Binder安装该_specific_版本。

另一种引脚版本号的方法是使用大于或等于签名(`>=`)，允许安装某个特定版本以上的任何版本。
当您有许多依赖关系并允许Binder找到一个不互相冲突的依赖关系的配置，同时避免任何先前的版本可能会中断或更改您的代码时，这将是有用的。

末尾。 您根本无法提供版本号 (仅为库/包的名称) ，Binder将安装该软件包的最新版本。
````

````{tabbed} Julia
在上述示例中，我们复制了一个散列到我们的 `Project.toml` 文件中，该文件与我们想安装的软件包版本有关。
对于完整的依赖关系图，我们还需要包含一个 `Manifest.toml` 文件，用于记录依赖关系的依赖关系。
在这两个文件之间，我们能够实例化朱利亚环境的确切复制。

当然，我们可以想象，随着环境的发展，相互依存关系变得更加复杂。 手写这些文件会变得很费力！
事实是，你从不手动操作，内置的软件包管理器 `Pkg` 可以[自动生成它们](https://julialang.github.io/Pkg.jl/v1/environments/)。
````

````{tabbed} R
在上面的例子中，我们指定了我们想要在我们的项目中使用R, 在`runtime.txt`中包含一个日期。
日期告诉BinderCRAN 快照要源 R 和包裹。
这些快照来自[RStudio Package Manager](https://packemanager.rstudio.com) (RSPM)。
在上面的例子中，使用了日期为`r-2022-01-01`的RSPM快照，当天R和`readr`的版本已安装。
为了示例工作流正常，请确保您不要早于此示例日期提供日期。

这为 R 用户提供了一些基本的软件包版本，但在 Python 的 `requires.txt` 中不像固定版本那么强大。
对于在 R 中固定的更强大和更具体的版本，请查看[`renv`](https://rstudio.github.io/renv/) 软件包。
````

1) 从 **添加 **Markdown** 代码片段<https://mybinder.org>** 到 `README.md` 文件在您的repo
## 5. 5. 检查环境

🚦🚦🚦

````{tabbed} Python
(1) 从发射面板上选出， 从笔记本部分中选择“Julia”来打开一个新的 Julia 笔记本
2) 键入一个新的单元：

   ```julia
   using Pkg
   Pkg。
   tatus()
   ```

3) 运行单元格以查看打印的版本号

   - 点击菜单栏中的 SHIFT+RETURN 或 "运行" 按钮
````

````{tabbed} Julia
(1) 从发射面板上选出， 从笔记本部分中选择“Julia”来打开一个新的 Julia 笔记本
2) 键入一个新的单元：

   ```julia
   using Pkg
   Pkg。 tatus()
   ```

3) 运行单元格以查看打印的版本号

   - 点击菜单栏中的 SHIFT+RETURN 或 "运行" 按钮
````

````{tabbed} R
(1) 从发射面板上选出， 从笔记本部分中选择“R”来打开一个新的 R 笔记本
2) 键入一个新的单元：

   ```r
   library(readr)
   packageVersion("readr")
   read_csv(system). ile("extdata/mtcars" sv", package = "readr"))
   ```

3) 运行单元格

    - 按菜单栏中的 SHIFT+RETURN 或 "运行"按钮
    你应该看到以下输出：
      - 已安装版本的 "readr"
      的版本号。
````

```{attention}
如果您保存这本笔记本，**不会** 保存到 GitHub 仓库中。
通过容器将更改推回到GitHub repo 是不可能的
**一旦您关闭浏览器窗口，您对Binder中的文件所作的任何更改都会丢失。
**
```

(z2b-step-6)=
## 6. 6. 分享您的工作

(z2b-小文件)=

- 分享 **https://mybinder.org/v2/gh/YOUR-USERNAME/my-first binder/HEAD** URL
- 访问 **[https://mybinder。 rg](https://mybinder.org)**, 输入你的仓库的 URL 并复制Markdown 或 Restructured 文本片段到你的 `README d` 文件。 这个代码片段将会呈现一个人们可以点击的徽章，看起来像这样： ![宾代尔](https://mybinder.org/badge_logo.svg)

🚦🚦🚦

对于最多 **10MB** 的文件来说，这是理想的。
   - 显示粘合剂徽章的灰色条将会展开以显示代码片段。 点击标记为“m”的方框旁边的剪贴板图标自动复制Markdown代码片段。 2) 点击徽章以确保它正常工作！

(z2b-中等文件) =
## 7. 7. 正在访问您的 Binder 中的数据

工程的另一种依赖关系是 **数据**。 根据您的数据大小和您分享数据的偏好，有不同的方式在您的位子里提供数据。

请参阅 [绑定的 `postBuilder` 示例](https://mybinder.readthedocs.io/en/latest/using/config_files.html#postbuild-run-code-after-installing-the-environment) 以了解 `postBuilding` 脚本。
### 小的公共文件

对于小型公共数据文件来说，最简单的方法是将它们直接添加到您的 GitHub 仓库中。 然后它们被直接封装到环境中，并与你的代码一起被翻译。

对于最多 **10MB** 的文件来说，这是理想的。

(z2b-private files)=
### 中等公共文件

若要访问介质文件 **从10s MB 至 几百MB**， 您可以将名为 `postBuilding` 的文件添加到您的仓库中。 `postBuild` 文件是一个 shell 脚本，作为图像构造的一部分执行，并且仅在构建新图像时执行一次。 不是每次启动Binder。

请参阅 [绑定的 `postBuilder` 示例](https://mybinder.readthedocs.io/en/latest/using/config_files.html#postbuild-run-code-after-installing-the-environment) 以了解 `postBuilding` 脚本。

```{note}
新的图像只是在Binder看到新的提交时才生成，而不是每次点击Binder链接。
因此，只是在构建Docker图像时才下载一次数据，而不是每次启动Binder。
```

为了支持访问私有文件， 您需要创建本地的 [BinderHub](https://binderhub.readthedocs.io) 部署，在那里您可以自行决定安全权衡。
### 大型公共文件

在你的GitHub repo 中放置大型文件或将它们直接放置在 Binder 生成的图像中是不切实际的。 大型文件的最佳选项是使用数据格式特有的库来流数据或按要求下载数据作为你代码的一部分。

出于安全考虑，您的流出流量仅限 HTTP/S 或 GitHub 连接。 您将无法使用 FTP 站点获取在 mybinder.org 上的数据。

(z2b-7步)=
### 私有文件

无法访问来自mybinder.org的非公开文件。 你应该把你的宾代里的所有信息都看作是公开的，意思是：

- 您的GitHub 仓库不应该有密码、令牌、密钥等等。
- 您不应将密码输入在 mybinder.org上运行的Binder；
- 您不应将您的私有SSH密钥或 API 代币上传到运行中的绑定器。

下面是运行 JupyterLab的 Binder 实例中的 URL 结构：

```{note}
建立一个BinderHub 并不是一项简单的任务，通常由信息技术/RSE 团体为了管理维护、安全和治理的原因而接管。
然而，这并不是说他们只是应该/可以建设一个宾德尔胡布的人群。
```

(z2b-8步)=
## 8. 8. 使用 `个帖子构建` 获取数据

🚦🚦🚦

````{tabbed} Python
1) 转到你的GitHub repo 并创建一个名为 `postBuild`
2) 的文件，在 `postBuild` 中添加一个单行内容：“wget -q -O gapminer”。 sv http://bit.ly/2uh4s3g`
   - `wget` 是一个程序，可以从 web 服务器检索内容。
     此行从 bitly URL 中提取内容并保存到由 `-O` 标志表示的文件名(大写字母"O")， 在本案中，`gapminer'不为零。
     目 录
     `-q`标志告诉`wget`悄悄地做这件事，这意味着它不会将任何东西打印到控制台。
3) 更新您的“要求”。 xt`文件添加了一个新行与 `pandas` 和另一个新行在 `matplotlib` 上的
   - 这些软件包没有必要下载数据，但我们将使用它们来读取CSV 文件并绘制图
4) 点击你README中的绑定标记来启动你的 Binder

一旦Binder 启动， 当你点击徽章时，你应该看到一个新的文件已经出现，它不是你的仓库的一部分。

现在通过创建一个新的笔记本(从笔记本部分选择"Python 3")来显示数据，然后在一个单元中运行以下代码。

```python
%matplotlib inline

impandas

data = pandas.read_csv("gapminder.csv", index_col="国家")

years = data olumns.str.strip("gdpPercap_") # 从每个列名称的最后4个字符中提取年份
data.colus = 年。 样式(int) # 将年份值转换为整数， 保存结果回到数据帧

数据。 oc[“澳大利亚”]。 lot()
```

```{note}
查看更多信息[Software Carpentry lesson](https://swcarpentry.github.io/python-novirgapminder/09-plotting/index.html)
```
```
````

````{tabbed} Julia
1) 转到你的GitHub repo 并创建一个名为 `postBuild`
2) 的文件，在 `postBuild` 中添加一个单行内容：“wget -q -O gapminer”。 sv http://bit.ly/2uh4s3g`
   - `wget` 是一个程序，可以从 web 服务器检索内容。
     此行从 bitly URL 中提取内容并保存到由 `-O` 标志表示的文件名(大写字母"O")， 在本案中，`gapminer'不为零。
     目 录
     `-q`标志告诉`wget`悄悄地做这件事，这意味着它不会将任何东西打印到控制台。
3) Update your `Project.toml` file by adding new dependencies to `[deps]` with the following lines:

   ```julia
   DataFrames = "a93c6f00-e57d-5684-b7b6-d8193f3e46c0"
   Plots = "91a5bcdd-55d7-5caf-9e0b-520d859cae80"
   ```

   - These packages aren't necessary to download the data but we will use them to read the CSV file and make a plot
4) Click the binder badge in your README to launch your Binder

Once the Binder has launched, you should see a new file has appeared that was not part of your repo when you clicked the badge.

现在通过创建一个新的笔记本(从笔记本部分选择“Julia”)和在单元中运行下面的代码来显示数据。

现在通过创建一个新的笔记本(从笔记本部分选择“Julia”)和在单元中运行下面的代码来显示数据。

```julia
using DataFrames
using CSV
using Plots

data = CSV.read("gapminder). sv", DataFrame)

# 提取对应澳大利亚的行
aus_gdp = data[data[:, :country] = “澳大利亚”，:]
aus_gdp = Matrix(Aus_gdp[:, ) :end])[:] # 作为矢量

# 从列名称中提取年份
years = [x[x[end-3:end] for x in names(datas)[2:end]]]
years = parse。 英寸、年份

# 绘图
绘图(年份、年份、年份)
```
````

````{tabbed} R
1) 转到你的GitHub repo 并创建一个名为 `postBuild`
2) 的文件，在 `postBuild` 中添加一个单行内容：“wget -q -O gapminer”。 sv http://bit.ly/2uh4s3g`
   - `wget` 是一个程序，可以从 web 服务器检索内容。
     此行从 bitly URL 中提取内容并保存到由 `-O` 标志表示的文件名(大写字母"O")， 在本案中，`gapminer'不为零。
     目 录
     `-q`标志告诉`wget`悄悄地做这件事，这意味着它不会将任何东西打印到控制台。
3) 更新您的 `install.R` 文件以安装两个额外的依赖关系，`tidyr` 和 `ggplot2`。 要做到这一点，请将所需软件包的字符矢量提供给`install.packes()`，而不是单个字符串。 现在安装命令应该像这样：

   ```r
   install。 ackages(c"readr", "tidyr", "ggplot2")
   ```

    - 这些软件包无需下载数据，但我们将使用它们来读取CSV文件， 处理它并绘制绘图
4) 点击你README中的粘合剂徽章来启动你的粘合剂

一旦绑定器启动， 当你点击徽章时，你应该看到一个新的文件已经出现，它不是你的仓库的一部分。 现在通过创建一个新的笔记本(从笔记本部分选择“R”)并在单元中运行以下代码来显示数据。

现在通过创建一个新的笔记本(从笔记本部分选择“R”)并在单元中运行以下代码来显示数据。

```r
library(readr)
library(tidyr)
library(ggplot2)

data <- read_csv("gapminer). sv") %>%
    vicot_longer(-国家
                 names_to = “年”，
                 values_to = "gdpPercap",
                 names_prefix = "gdpPercap_",
                 names_transversion = list(year = as). \nteger)

data [data$country == "澳大利亚", ] %>%
    ggglot(aesx = year. y = gdpPercap)) +
    geom_line()
```
````
(z2b-beyond-notebooks)=
## 更改接口
在本教程中，我们一直在使用JupyterLab 界面。 这是新创建的 Binder 实例的默认接口。 然而，这并不是在mybinder.org、 经典笔记本视图和RStudio上可用的唯一界面。 (RStudio需要安装 R 环境才能使用。
) 您可以以不同方式访问不同的接口。 最简单的方法是在JupyterLauncher中使用按钮。 但您可以提供直接打开特定接口的 URL 参数 (或文件! 当Binder实例启动时。 我们现在将覆盖你可以操纵你的 Binder URL来导航接口之间的三种方式。
### 从正在运行的 Binder
下面是运行 JupyterLab的 Binder 实例中的 URL 结构：
> **https://<some-prefix>.mybinder.org/user/<a composite of your username, repo name and a hash>/lab** You can change the interface from JupyterLab to either the Classic Notebook or RStudio by changing the `/lab` part of the URL to: - **Classic Notebook:** `/tree` - **RStudio:** `/rstudio`
### by changing the mybinder.org launch link
Here is the launch link you have been using throughout this tutorial:
> **https://mybinder.org/v2/gh/YOUR-USERNAME/my-first-binder/HEAD** You can access each interface by appending once of the following to the end of you URL: - **Jupyter Notebook:** `?urlpath=tree` - **JupyterLab:** `?urlpath=lab` - **RStudio:** `?urlpath=rstudio`
### by using the mybinder.org form
You can also set the interface when constructing your launch link on the mybinder.org website (instead of editing the URL directly) as demonstrated in the below gif.

```{figure} https://user-images.githubusercontent.com/1448859/53651127-4dabe900-3c46-11e9-8684-2cfde840d4ce.gif
---
name: changing_interfaces
alt: A gif demonstrating how to change the interface of a Binder on the mybinder.org website
---
Use the "URL to open" option on the mybinder.org site to select your interface
```

(z2b-over-to-you)=
## Now over to you!

Now you've binderized (bound?) this demo repo, it's time to binderize the example script and data you brought along!

**Some useful links:**

- Choosing languages:
  - **<https://mybinder.readthedocs.io/en/latest/howto/languages.html>**
- Configuration files:
  - **<https://mybinder.readthedocs.io/en/latest/using/config_files.html>**
- Example Binder repos:
  - **<https://mybinder.readthedocs.io/en/latest/sample_repos.html>**
- Getting data:
  - With `wget`: **<https://github.com/binder-examples/getting-data>**
  - With `quilt`: **<https://github.com/binder-examples/data-quilt>**
  - From remote storage: **<https://github.com/binder-examples/remote_storage>**

**Advanced usage patterns:**

- Separating content from envorinment with `nbgitpuller` to reduced rebuilds:
  - **<https://discourse.jupyter.org/t/tip-speed-up-binder-launches-by-pulling-github-content-in-a-binder-link-with-nbgitpuller/922>**
- Tips for reducing the start-up time of your repository:
  - **<https://discourse.jupyter.org/t/how-to-reduce-mybinder-org-repository-startup-time/4956>**
