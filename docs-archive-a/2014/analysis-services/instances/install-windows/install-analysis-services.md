---
title: Instalar Analysis Services no modo de tabela | Microsoft Docs
ms.custom: ''
ms.date: 03/09/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: cd6ac80d-b735-4e3e-a024-489f1409ad33
author: minewiskan
ms.author: owend
ms.openlocfilehash: a677fd7770f646067cafb8fedf6d3705ccf2de3c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679578"
---
# <a name="install-analysis-services-in-tabular-mode"></a><span data-ttu-id="67beb-102">Instalar o Analysis Services em modo Tabular</span><span class="sxs-lookup"><span data-stu-id="67beb-102">Install Analysis Services in Tabular Mode</span></span>
  <span data-ttu-id="67beb-103">Se você estiver instalando o Analysis Services para usar os novos recursos de modelagem tabular, você deverá instalar o Analysis Services em um modo de servidor que dá suporte a esse tipo de modelo.</span><span class="sxs-lookup"><span data-stu-id="67beb-103">If you are installing Analysis Services to use the new tabular modeling features, you must install Analysis Services in a server mode that supports that type of model.</span></span> <span data-ttu-id="67beb-104">O modo de servidor é Tabular, e é configurado durante a instalação.</span><span class="sxs-lookup"><span data-stu-id="67beb-104">The server mode is Tabular, and it is configured during installation.</span></span>  
  
 <span data-ttu-id="67beb-105">Depois de instalar o servidor nesse modo, você poderá usá-lo para hospedar soluções que você cria no designer de modelo tabular.</span><span class="sxs-lookup"><span data-stu-id="67beb-105">After you install the server in this mode, you can use it host solutions that you build in tabular model designer.</span></span> <span data-ttu-id="67beb-106">Um servidor de modo tabular é exigido se você desejar acesso de dados de modelo tabular pela rede.</span><span class="sxs-lookup"><span data-stu-id="67beb-106">A tabular mode server is required if you want tabular model data access over the network.</span></span>  
  
 <span data-ttu-id="67beb-107">Você pode especificar o modo Tabular no Assistente de Instalação ou em uma instalação de linha de comando.</span><span class="sxs-lookup"><span data-stu-id="67beb-107">You can specify Tabular mode in the Installation Wizard or in a command line setup.</span></span> <span data-ttu-id="67beb-108">As seções a seguir descrevem cada tipo de abordagem.</span><span class="sxs-lookup"><span data-stu-id="67beb-108">The following sections describe each approach.</span></span>  
  
## <a name="installation-wizard"></a><span data-ttu-id="67beb-109">Assistente de instalação</span><span class="sxs-lookup"><span data-stu-id="67beb-109">Installation Wizard</span></span>  
 <span data-ttu-id="67beb-110">A lista a seguir mostra a você quais páginas no assistente de Instalação do SQL Server são usadas para instalar o Analysis Services em modo Tabular:</span><span class="sxs-lookup"><span data-stu-id="67beb-110">The following list shows you which pages in the SQL Server Installation wizard are used to install Analysis Services in Tabular mode:</span></span>  
  
1.  <span data-ttu-id="67beb-111">Selecione o **Analysis Services** na Árvore de Recursos na Instalação.</span><span class="sxs-lookup"><span data-stu-id="67beb-111">Select **Analysis Services** from the Feature Tree in Setup.</span></span>  
  
     <span data-ttu-id="67beb-112">![Árvore de recursos de instalação mostrando o Analysis Services](../../../sql-server/install/media/ssas-setupas.gif "Árvore de recursos de instalação mostrando o Analysis Services")</span><span class="sxs-lookup"><span data-stu-id="67beb-112">![Setup feature tree showing Analsyis Services](../../../sql-server/install/media/ssas-setupas.gif "Setup feature tree showing Analsyis Services")</span></span>  
  
2.  <span data-ttu-id="67beb-113">Na página de Configuração do Analysis Services, selecione o **Modo de Tabela**.</span><span class="sxs-lookup"><span data-stu-id="67beb-113">On the Analysis Services Configuration page, be sure to select **Tabular Mode**.</span></span>  
  
     <span data-ttu-id="67beb-114">![Página de instalação com as opções de configuração do Analysis Services](../../../sql-server/install/media/ssas-setupasconfig.gif "Página de instalação com as opções de configuração do Analysis Services")</span><span class="sxs-lookup"><span data-stu-id="67beb-114">![Setup page with Analysis Services config options](../../../sql-server/install/media/ssas-setupasconfig.gif "Setup page with Analysis Services config options")</span></span>  
  
 <span data-ttu-id="67beb-115">O modo Tabular usa o índice columnstore xVelocity de memória otimizada (VertiPaq), que é o armazenamento padrão para modelos tabulares que você implanta no Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="67beb-115">Tabular mode uses the xVelocity in-memory analytics engine (VertiPaq), which is the default storage for tabular models that you deploy to Analysis Services.</span></span> <span data-ttu-id="67beb-116">Depois de implantar soluções de modelo tabular no servidor, você pode configurar seletivamente soluções tabulares para usar o armazenamento em disco DirectQuery como uma alternativa ao armazenamento associada à memória.</span><span class="sxs-lookup"><span data-stu-id="67beb-116">After you deploy tabular model solutions to the server, you can selectively configure tabular solutions to use DirectQuery disk storage as an alternative to memory-bound storage.</span></span>  
  
## <a name="command-line-setup"></a><span data-ttu-id="67beb-117">Instalação de Linha de Comando</span><span class="sxs-lookup"><span data-stu-id="67beb-117">Command Line Setup</span></span>  
 <span data-ttu-id="67beb-118">A Instalação do SQL Server inclui um novo parâmetro (`ASSERVERMODE`) que especifica o modo do servidor.</span><span class="sxs-lookup"><span data-stu-id="67beb-118">SQL Server Setup includes a new parameter (`ASSERVERMODE`) that specifies the server mode.</span></span> <span data-ttu-id="67beb-119">O exemplo a seguir ilustra a instalação de linha de comando que instala o Analysis Services no modo de servidor Tabular.</span><span class="sxs-lookup"><span data-stu-id="67beb-119">The following example illustrates a command line setup that installs Analysis Services in Tabular server mode.</span></span>  
  
```  
  
Setup.exe /q /IAcceptSQLServerLicenseTerms /ACTION=install /FEATURES=AS /ASSERVERMODE=TABULAR /INSTANCENAME=ASTabular /INDICATEPROGRESS/ASSVCACCOUNT=<DomainName\UserName> /ASSVCPASSWORD=<StrongPassword> /ASSYSADMINACCOUNTS=<DomainName\UserName>   
```  
  
 <span data-ttu-id="67beb-120">`INSTANCENAME` deve ter menos de 17 caracteres.</span><span class="sxs-lookup"><span data-stu-id="67beb-120">`INSTANCENAME` must be less than 17 characters.</span></span>  
  
 <span data-ttu-id="67beb-121">Todos os valores de conta de espaço reservado devem ser substituídos por contas e senhas válidas.</span><span class="sxs-lookup"><span data-stu-id="67beb-121">All placeholder account values must be replaced with valid accounts and password.</span></span>  
  
 <span data-ttu-id="67beb-122">Ferramentas como o SQL Server Management Studio ou [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)] não são instaladas usando a sintaxe de linha de comando de exemplo que é fornecida.</span><span class="sxs-lookup"><span data-stu-id="67beb-122">Tools such as SQL Server Management Studio or [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)] are not installed using the example command line syntax that is provided.</span></span> <span data-ttu-id="67beb-123">Para obter mais informações sobre como adicionar recursos, consulte [instalar SQL Server 2014 no prompt de comando](../../../database-engine/install-windows/install-sql-server-from-the-command-prompt.md).</span><span class="sxs-lookup"><span data-stu-id="67beb-123">For more information about adding features, see [Install SQL Server 2014 from the Command Prompt](../../../database-engine/install-windows/install-sql-server-from-the-command-prompt.md).</span></span>  
  
 <span data-ttu-id="67beb-124">`ASSERVERMODE` diferencia maiúsculas e minúsculas.</span><span class="sxs-lookup"><span data-stu-id="67beb-124">`ASSERVERMODE` is case-sensitive.</span></span>  <span data-ttu-id="67beb-125">Todos os valores devem ser expressos em maiúsculas.</span><span class="sxs-lookup"><span data-stu-id="67beb-125">All values must be expressed in upper case.</span></span> <span data-ttu-id="67beb-126">A tabela a seguir descreve os valores válidos para `ASSERVERMODE`.</span><span class="sxs-lookup"><span data-stu-id="67beb-126">The following table describes the valid values for `ASSERVERMODE`.</span></span>  
  
|<span data-ttu-id="67beb-127">Valor</span><span class="sxs-lookup"><span data-stu-id="67beb-127">Value</span></span>|<span data-ttu-id="67beb-128">Descrição</span><span class="sxs-lookup"><span data-stu-id="67beb-128">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="67beb-129">MULTIDIMENSIONAL</span><span class="sxs-lookup"><span data-stu-id="67beb-129">MULTIDIMENSIONAL</span></span>|<span data-ttu-id="67beb-130">Este é o valor padrão.</span><span class="sxs-lookup"><span data-stu-id="67beb-130">This is the default value.</span></span> <span data-ttu-id="67beb-131">Se você não configurar o `ASSERVERMODE`, o servidor será instalado no modo de servidor Multidimensional.</span><span class="sxs-lookup"><span data-stu-id="67beb-131">If you do not set `ASSERVERMODE`, the server is installed in Multidimensional server mode.</span></span>|  
|<span data-ttu-id="67beb-132">POWERPIVOT</span><span class="sxs-lookup"><span data-stu-id="67beb-132">POWERPIVOT</span></span>|<span data-ttu-id="67beb-133">Esse valor é opcional.</span><span class="sxs-lookup"><span data-stu-id="67beb-133">This value is optional.</span></span> <span data-ttu-id="67beb-134">Na prática, se você configura o parâmetro `ROLE`, o modo de servidor é automaticamente definido como 1, tornando `ASSERVERMODE` opcional para uma instalação do PowerPivot para SharePoint.</span><span class="sxs-lookup"><span data-stu-id="67beb-134">In practice, if you set the `ROLE` parameter, the server mode is automatically set to 1, making `ASSERVERMODE` optional for a PowerPivot for SharePoint installation.</span></span> <span data-ttu-id="67beb-135">Para obter mais informações, consulte [Install PowerPivot from the Command Prompt](../../../sql-server/install/install-powerpivot-from-the-command-prompt.md).</span><span class="sxs-lookup"><span data-stu-id="67beb-135">For more information, see [Install PowerPivot from the Command Prompt](../../../sql-server/install/install-powerpivot-from-the-command-prompt.md).</span></span>|  
|<span data-ttu-id="67beb-136">TABULAR</span><span class="sxs-lookup"><span data-stu-id="67beb-136">TABULAR</span></span>|<span data-ttu-id="67beb-137">Esse valor é obrigatório se você estiver instalando o Analysis Services no modo Tabular usando a instalação de linha de comando.</span><span class="sxs-lookup"><span data-stu-id="67beb-137">This value is required if you are installing Analysis Services in Tabular mode using command line setup.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="67beb-138">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="67beb-138">See Also</span></span>  
 <span data-ttu-id="67beb-139">[Determinar o modo de servidor de uma instância de Analysis Services](../determine-the-server-mode-of-an-analysis-services-instance.md) </span><span class="sxs-lookup"><span data-stu-id="67beb-139">[Determine the Server Mode of an Analysis Services Instance](../determine-the-server-mode-of-an-analysis-services-instance.md) </span></span>  
 <span data-ttu-id="67beb-140">[Configurar o acesso na memória ou DirectQuery para um banco de dados modelo de tabela](../../tabular-models/enable-directquery-mode-in-ssms.md) </span><span class="sxs-lookup"><span data-stu-id="67beb-140">[Configure In-Memory or DirectQuery Access for a Tabular Model Database](../../tabular-models/enable-directquery-mode-in-ssms.md) </span></span>  
 [<span data-ttu-id="67beb-141">Modelagem de tabela &#40;SSAS de tabela&#41;</span><span class="sxs-lookup"><span data-stu-id="67beb-141">Tabular Modeling &#40;SSAS Tabular&#41;</span></span>](../../tabular-models/tabular-models-ssas.md)  
  
  
