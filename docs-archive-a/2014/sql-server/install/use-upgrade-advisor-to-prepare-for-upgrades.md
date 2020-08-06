---
title: Usar o supervisor de atualização para se preparar para atualizações | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- Upgrade Advisor [SQL Server]
- upgrading SQL Server, Upgrade Advisor
- upgrading SQL Server, preparing to upgrade
- SQL Server Upgrade Advisor
- analyzing installations for upgrading [SQL Server]
ms.assetid: d85b0833-ddeb-42e3-9397-97ea60d521b7
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: e53d895cb19a172d0810ae9d6c2bda3406732da1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680745"
---
# <a name="use-upgrade-advisor-to-prepare-for-upgrades"></a><span data-ttu-id="e2e1a-102">Usar o Supervisor de Atualização para preparar para atualizações</span><span class="sxs-lookup"><span data-stu-id="e2e1a-102">Use Upgrade Advisor to Prepare for Upgrades</span></span>
  <span data-ttu-id="e2e1a-103">O Supervisor de Atualização do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ajuda você a se preparar para atualizações do [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e2e1a-103">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Upgrade Advisor helps you prepare for upgrades to [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="e2e1a-104">O Supervisor de Atualização analisa os componentes instalados de versões anteriores do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e gera um relatório que identifica os problemas a serem corrigidos antes ou depois da atualização.</span><span class="sxs-lookup"><span data-stu-id="e2e1a-104">Upgrade Advisor analyzes installed components from earlier versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], and then generates a report that identifies issues to fix either before or after you upgrade.</span></span>  
  
## <a name="how-upgrade-advisor-works"></a><span data-ttu-id="e2e1a-105">Como o Supervisor de Atualização funciona</span><span class="sxs-lookup"><span data-stu-id="e2e1a-105">How Upgrade Advisor Works</span></span>  
 <span data-ttu-id="e2e1a-106">Quando você executa o supervisor de atualização, a home page do supervisor de atualização é exibida.</span><span class="sxs-lookup"><span data-stu-id="e2e1a-106">When you run Upgrade Advisor, the Upgrade Advisor Home page appears.</span></span> <span data-ttu-id="e2e1a-107">Na página inicial, você pode executar as seguintes ferramentas:</span><span class="sxs-lookup"><span data-stu-id="e2e1a-107">From the Home page, you can run the following tools:</span></span>  
  
-   <span data-ttu-id="e2e1a-108">Assistente para Análise do Supervisor de Atualização</span><span class="sxs-lookup"><span data-stu-id="e2e1a-108">Upgrade Advisor Analysis Wizard</span></span>  
  
-   <span data-ttu-id="e2e1a-109">Visualizador de Relatórios do Supervisor de Atualização</span><span class="sxs-lookup"><span data-stu-id="e2e1a-109">Upgrade Advisor Report Viewer</span></span>  
  
-   <span data-ttu-id="e2e1a-110">Tópicos da Ajuda do Supervisor de Atualização</span><span class="sxs-lookup"><span data-stu-id="e2e1a-110">Upgrade Advisor Help</span></span>  
  
 <span data-ttu-id="e2e1a-111">Ao usar o Supervisor de Atualização pela primeira vez, execute o Assistente para Análise do Supervisor de Atualização a fim de analisar os componentes do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e2e1a-111">The first time that you use Upgrade Advisor, run the Upgrade Advisor Analysis Wizard to analyze [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] components.</span></span> <span data-ttu-id="e2e1a-112">Quando o assistente concluir a análise, exiba os relatórios resultantes no Visualizador de Relatórios do Supervisor de Atualização.</span><span class="sxs-lookup"><span data-stu-id="e2e1a-112">When the wizard finishes the analysis, view the resulting reports in the Upgrade Advisor Report Viewer.</span></span> <span data-ttu-id="e2e1a-113">Cada relatório fornece links para informações na Ajuda do Supervisor de Atualização que ajudarão a corrigir ou reduzir o efeito dos problemas conhecidos.</span><span class="sxs-lookup"><span data-stu-id="e2e1a-113">Each report provides links to information in Upgrade Advisor Help that will help you fix or reduce the effect of the known issues.</span></span>  
  
## <a name="upgrade-advisor-analysis"></a><span data-ttu-id="e2e1a-114">Análise do Supervisor de Atualização</span><span class="sxs-lookup"><span data-stu-id="e2e1a-114">Upgrade Advisor Analysis</span></span>  
 <span data-ttu-id="e2e1a-115">O Supervisor de Atualização analisa os seguintes componentes do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="e2e1a-115">Upgrade Advisor analyzes the following [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] components:</span></span>  
  
-   [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
-   [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]  
  
-   [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]  
  
-   [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)]  
  
 <span data-ttu-id="e2e1a-116">A análise examina os objetos que podem ser acessados, como scripts, procedimentos armazenados, gatilhos e arquivos de rastreamento.</span><span class="sxs-lookup"><span data-stu-id="e2e1a-116">The analysis examines objects that can be accessed, such as scripts, stored procedures, triggers, and trace files.</span></span> <span data-ttu-id="e2e1a-117">O Supervisor de Atualização não pode analisar aplicativos da área de trabalho ou procedimentos armazenados criptografados.</span><span class="sxs-lookup"><span data-stu-id="e2e1a-117">Upgrade Advisor cannot analyze desktop applications or encrypted stored procedures.</span></span>  
  
 <span data-ttu-id="e2e1a-118">A saída é feita no formato de um relatório XML.</span><span class="sxs-lookup"><span data-stu-id="e2e1a-118">Output is in the form of an XML report.</span></span> <span data-ttu-id="e2e1a-119">Exiba o relatório XML usando o Visualizador de Relatórios do Supervisor de Atualização.</span><span class="sxs-lookup"><span data-stu-id="e2e1a-119">View the XML report by using the Upgrade Advisor report viewer.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e2e1a-120">Os relatórios podem conter um item "outros problemas de atualização".</span><span class="sxs-lookup"><span data-stu-id="e2e1a-120">Reports might contain an "other upgrade issues" item.</span></span> <span data-ttu-id="e2e1a-121">Esse item é vinculado a uma lista de problemas que não são detectados pelo Supervisor de Atualização, mas que podem existir em seu servidor ou em seus aplicativos.</span><span class="sxs-lookup"><span data-stu-id="e2e1a-121">This item links to a list of issues that are not detected by Upgrade Advisor, but might exist on your server or in your applications.</span></span> <span data-ttu-id="e2e1a-122">Você deve revisar a lista de problemas não detectáveis e determinar se deve alterar seu servidor ou seus aplicativos devido aos problemas não detectáveis.</span><span class="sxs-lookup"><span data-stu-id="e2e1a-122">You should review the list of undetectable issues and determine whether you must change your server or applications because of the undetectable issues.</span></span>  
  
## <a name="how-to-install-and-run-upgrade-advisor"></a><span data-ttu-id="e2e1a-123">Como instalar e executar o Supervisor de Atualização</span><span class="sxs-lookup"><span data-stu-id="e2e1a-123">How to Install and Run Upgrade Advisor</span></span>  
 <span data-ttu-id="e2e1a-124">O local onde você instala o Aconselhador de Atualização do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] depende do que você irá analisar.</span><span class="sxs-lookup"><span data-stu-id="e2e1a-124">The location where you install [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Upgrade Advisor depends on what you will be analyzing.</span></span> <span data-ttu-id="e2e1a-125">O Supervisor de Atualização dá suporte à análise remota de todos os componentes com suporte, exceto o [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e2e1a-125">Upgrade Advisor supports remote analysis of all supported components except [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span></span> <span data-ttu-id="e2e1a-126">Se não estiver examinando instâncias do [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], você poderá instalar o Supervisor de Atualização em qualquer computador que possa se conectar à sua instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e que atenda aos pré-requisitos do Supervisor de Atualização.</span><span class="sxs-lookup"><span data-stu-id="e2e1a-126">If you are not scanning instances of [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], you can install Upgrade Advisor on any computer that can connect to your instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], and that meets the Upgrade Advisor prerequisites.</span></span> <span data-ttu-id="e2e1a-127">Para obter mais informações, consulte [Atualizações de versão e edição com suporte](../../database-engine/install-windows/supported-version-and-edition-upgrades.md).</span><span class="sxs-lookup"><span data-stu-id="e2e1a-127">For more information, see [Supported Version and Edition Upgrades](../../database-engine/install-windows/supported-version-and-edition-upgrades.md).</span></span> <span data-ttu-id="e2e1a-128">Se você estiver verificando instâncias do [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], será necessário instalar o Supervisor de Atualização no servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="e2e1a-128">If you are scanning instances of [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], you must install Upgrade Advisor on the report server.</span></span>  
  
 <span data-ttu-id="e2e1a-129">O Supervisor de Atualização está disponível em um pacote de recursos.</span><span class="sxs-lookup"><span data-stu-id="e2e1a-129">Upgrade Advisor is available in a feature pack.</span></span>  
  
 <span data-ttu-id="e2e1a-130">Os pré-requisitos para instalar e executar o supervisor de atualização são os seguintes:</span><span class="sxs-lookup"><span data-stu-id="e2e1a-130">Prerequisites for installing and running Upgrade Advisor are as follows:</span></span>  
  
-   [!INCLUDE[firstref_longhorn](../../includes/firstref-longhorn-md.md)] <span data-ttu-id="e2e1a-131">SP2, Windows 7 SP1 e [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)] SP1.</span><span class="sxs-lookup"><span data-stu-id="e2e1a-131">SP2, Windows 7 SP1, and [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)] SP1.</span></span>  
  
-   <span data-ttu-id="e2e1a-132">Windows Installer desde a versão 4.5.</span><span class="sxs-lookup"><span data-stu-id="e2e1a-132">Windows Installer beginning with version 4.5.</span></span> <span data-ttu-id="e2e1a-133">Você pode instalar o Windows Installer do [site do Windows Installer](https://www.microsoft.com/download/details.aspx?id=8483).</span><span class="sxs-lookup"><span data-stu-id="e2e1a-133">You can install Windows Installer from the [Windows Installer Web site](https://www.microsoft.com/download/details.aspx?id=8483).</span></span>  
  
-   <span data-ttu-id="e2e1a-134">Microsoft .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="e2e1a-134">Microsoft .NET Framework 4.</span></span> <span data-ttu-id="e2e1a-135">.NET Framework 4 está disponível na [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mídia do produto e na página de [download do .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=209895).</span><span class="sxs-lookup"><span data-stu-id="e2e1a-135">.NET Framework 4 is available on the [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] product media, and from the [.NET Framework 4 download page](https://go.microsoft.com/fwlink/?LinkId=209895).</span></span>  
  
    -   <span data-ttu-id="e2e1a-136">Para instalar o .NET Framework 4 a partir da mídia do [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], localize a raiz da unidade de disco.</span><span class="sxs-lookup"><span data-stu-id="e2e1a-136">To install the .NET Framework 4 from the [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] media, locate the root of the disk drive.</span></span> <span data-ttu-id="e2e1a-137">Clique duas vezes nas pastas \redist e DotNetFrameworks; execute o dotNetFx40_Full_x86_x64.exe (para sistemas operacionais de 32 ou 64 bits).</span><span class="sxs-lookup"><span data-stu-id="e2e1a-137">Then, double-click the \redist folder, double-click the DotNetFrameworks folder, and run dotNetFx40_Full_x86_x64.exe (for 32-bit operating systems or for 64-bit operating systems).</span></span>  
  
 <span data-ttu-id="e2e1a-138">Para instalar o Supervisor de Atualização a partir da Web, clique no botão de download na página de download.</span><span class="sxs-lookup"><span data-stu-id="e2e1a-138">To install Upgrade Advisor from the Web, click the download button on the download page.</span></span> <span data-ttu-id="e2e1a-139">Você poderá executar a instalação imediatamente ou salvar o arquivo SQLUA.msi para execução posterior.</span><span class="sxs-lookup"><span data-stu-id="e2e1a-139">You can then run installation immediately, or save the SQLUA.msi file to run later.</span></span> <span data-ttu-id="e2e1a-140">Se você estiver instalando do disco do produto, execute SQLUA.msi diretamente do disco do produto.</span><span class="sxs-lookup"><span data-stu-id="e2e1a-140">If you are installing from the product disc, run SQLUA.msi directly from the product disk.</span></span>  
  
 <span data-ttu-id="e2e1a-141">Depois de instalar o supervisor de atualização, você pode abri-lo no menu **Iniciar** :</span><span class="sxs-lookup"><span data-stu-id="e2e1a-141">After you install Upgrade Advisor, you can open it from the **Start** menu:</span></span>  
  
-   <span data-ttu-id="e2e1a-142">Clique em **Iniciar**, aponte para **todos os programas**, aponte para [!INCLUDE[ssCurrentUI](../../includes/sscurrentui-md.md)] e clique em \*\* [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] supervisor de atualização\*\*.</span><span class="sxs-lookup"><span data-stu-id="e2e1a-142">Click **Start**, point to **All Programs**, point to [!INCLUDE[ssCurrentUI](../../includes/sscurrentui-md.md)], and then click **[!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] Upgrade Advisor**.</span></span>  
  
 <span data-ttu-id="e2e1a-143">Para obter mais informações, consulte a documentação do Supervisor de Atualização incluída no download do Supervisor de Atualização e nas Notas de Versão do [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e2e1a-143">For more information, see the Upgrade Advisor documentation included in the Upgrade Advisor download and the [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] Release Notes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e2e1a-144">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="e2e1a-144">See Also</span></span>  
 <span data-ttu-id="e2e1a-145">[Trabalhar com várias versões e instâncias do SQL Server](../../../2014/sql-server/install/work-with-multiple-versions-and-instances-of-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="e2e1a-145">[Work with Multiple Versions and Instances of SQL Server](../../../2014/sql-server/install/work-with-multiple-versions-and-instances-of-sql-server.md) </span></span>  
 <span data-ttu-id="e2e1a-146">[Atualizações de versão e edição com suporte](../../database-engine/install-windows/supported-version-and-edition-upgrades.md) </span><span class="sxs-lookup"><span data-stu-id="e2e1a-146">[Supported Version and Edition Upgrades](../../database-engine/install-windows/supported-version-and-edition-upgrades.md) </span></span>  
 [<span data-ttu-id="e2e1a-147">Compatibilidade com versões anteriores</span><span class="sxs-lookup"><span data-stu-id="e2e1a-147">Backward Compatibility</span></span>](../../../2014/getting-started/backward-compatibility.md)  
  
  
