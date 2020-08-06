---
title: Propriedades do SQL Server (guia Avançado) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
ms.assetid: 2ffd10fd-bac1-478f-9cff-96ed6c8b787f
author: stevestein
ms.author: sstein
ms.openlocfilehash: a9a77fd0a43627b49bb8719f6fa943408f64fcca
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87568987"
---
# <a name="sql-server-properties-advanced-tab"></a><span data-ttu-id="ade72-102">Propriedades do SQL Server (guia Avançado)</span><span class="sxs-lookup"><span data-stu-id="ade72-102">SQL Server Properties (Advanced Tab)</span></span>
  <span data-ttu-id="ade72-103">As propriedades a seguir aparecem por padrão na guia **Avançado** .</span><span class="sxs-lookup"><span data-stu-id="ade72-103">The following properties appear on the **Advanced** tab by default.</span></span> <span data-ttu-id="ade72-104">Se as propriedades personalizadas estiverem definidas, elas também aparecerão nessa guia com seus valores.</span><span class="sxs-lookup"><span data-stu-id="ade72-104">If custom properties are defined, they also appear on this tab, with their values.</span></span>  
  
## <a name="options"></a><span data-ttu-id="ade72-105">Opções</span><span class="sxs-lookup"><span data-stu-id="ade72-105">Options</span></span>  
 <span data-ttu-id="ade72-106">**Clusterizado**</span><span class="sxs-lookup"><span data-stu-id="ade72-106">**Clustered**</span></span>  
 <span data-ttu-id="ade72-107">Indica se este serviço for instalado como um recurso de um servidor clusterizado.</span><span class="sxs-lookup"><span data-stu-id="ade72-107">Indicates if this service is installed as a resource of a clustered server.</span></span>  
  
 <span data-ttu-id="ade72-108">**Relatório de Comentários do Cliente**</span><span class="sxs-lookup"><span data-stu-id="ade72-108">**Customer Feedback Reporting**</span></span>  
 <span data-ttu-id="ade72-109">Indica se o Monitoramento da Qualidade do Serviço foi habilitado neste serviço.</span><span class="sxs-lookup"><span data-stu-id="ade72-109">Indicates whether Service Quality Monitoring has been enabled on this service.</span></span> <span data-ttu-id="ade72-110">Para obter mais informações sobre o Relatório de Comentários do Cliente, pesquise "Configurações de relatório de erro e uso" nos Manuais Online.</span><span class="sxs-lookup"><span data-stu-id="ade72-110">For more information on Customer Feedback Reporting, search Books Online for the topic, "Error and Usage Report Settings."</span></span>  
  
 <span data-ttu-id="ade72-111">**Caminho de Dados**</span><span class="sxs-lookup"><span data-stu-id="ade72-111">**Data Path**</span></span>  
 <span data-ttu-id="ade72-112">Exibe o caminho para os binários do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] desta instalação do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ade72-112">Displays the path to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] binaries for this installation of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="ade72-113">**Diretório de Despejo**</span><span class="sxs-lookup"><span data-stu-id="ade72-113">**Dump Directory**</span></span>  
 <span data-ttu-id="ade72-114">Exibe o local em que os despejos de memória são colocadas no caso de um erro.</span><span class="sxs-lookup"><span data-stu-id="ade72-114">Displays the location where memory dumps are placed in case of an error.</span></span>  
  
 <span data-ttu-id="ade72-115">**Relatório de Erros**</span><span class="sxs-lookup"><span data-stu-id="ade72-115">**Error Reporting**</span></span>  
 <span data-ttu-id="ade72-116">Quando definido como **Sim**, o programa Dr. Watson encaminhará informações para a [!INCLUDE[msCoName](../../includes/msconame-md.md)] ou para o servidor de erro, se ocorrer uma falha grave.</span><span class="sxs-lookup"><span data-stu-id="ade72-116">When set to **Yes**, the Dr. Watson program forwards information to either [!INCLUDE[msCoName](../../includes/msconame-md.md)] or your error server if a serious failure occurs.</span></span> <span data-ttu-id="ade72-117">Para obter mais informações sobre o Relatório de Erros, pesquise "Configurações de relatório de erro e uso" nos Manuais Online.</span><span class="sxs-lookup"><span data-stu-id="ade72-117">For more information on Error Reporting, search Books Online for the topic, "Error and Usage Report Settings."</span></span> <span data-ttu-id="ade72-118">Para alterar esse valor, no Pesquisador de Objetos do [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] , clique com o botão direito do mouse no seu servidor, clique em **Propriedades**e clique na página **Diversas Configurações de Servidor** .</span><span class="sxs-lookup"><span data-stu-id="ade72-118">To change this value, in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] Object Explorer, right-click your server, click **Properties**, and then click the **Misc. Server Settings** page.</span></span> <span data-ttu-id="ade72-119">As opções são apresentadas na área **Relatório de Informações** .</span><span class="sxs-lookup"><span data-stu-id="ade72-119">The options are presented in the **Information Reporting** area.</span></span>  
  
 <span data-ttu-id="ade72-120">**Versão do Arquivo**</span><span class="sxs-lookup"><span data-stu-id="ade72-120">**File Version**</span></span>  
 <span data-ttu-id="ade72-121">Exibe a versão do executável do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ade72-121">Displays the version of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] executable.</span></span>  
  
 <span data-ttu-id="ade72-122">**Caminho de Instalação**</span><span class="sxs-lookup"><span data-stu-id="ade72-122">**Install Path**</span></span>  
 <span data-ttu-id="ade72-123">Exibe o caminho para os binários do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] desta instalação do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ade72-123">Displays the path to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] binaries for this installation of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="ade72-124">**ID da Instância**</span><span class="sxs-lookup"><span data-stu-id="ade72-124">**Instance ID**</span></span>  
 <span data-ttu-id="ade72-125">Indica a instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que usou este serviço.</span><span class="sxs-lookup"><span data-stu-id="ade72-125">Indicates the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance that used this service.</span></span>  
  
 <span data-ttu-id="ade72-126">**Idioma**</span><span class="sxs-lookup"><span data-stu-id="ade72-126">**Language**</span></span>  
 <span data-ttu-id="ade72-127">Exibe o idioma padrão das mensagens do servidor.</span><span class="sxs-lookup"><span data-stu-id="ade72-127">Displays the default language for server messages.</span></span>  
  
 <span data-ttu-id="ade72-128">**Raiz do Registro**</span><span class="sxs-lookup"><span data-stu-id="ade72-128">**Registry Root**</span></span>  
 <span data-ttu-id="ade72-129">Exibe o local das chaves do Registro usadas por este aplicativo.</span><span class="sxs-lookup"><span data-stu-id="ade72-129">Displays the location of the registry keys used by this application.</span></span>  
  
 <span data-ttu-id="ade72-130">**Nível do Service Pack**</span><span class="sxs-lookup"><span data-stu-id="ade72-130">**Service Pack Level**</span></span>  
 <span data-ttu-id="ade72-131">Exibe o nível do service pack desta instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ade72-131">Displays the service pack level of this instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="ade72-132">**Nome do SKU**</span><span class="sxs-lookup"><span data-stu-id="ade72-132">**SKU Name**</span></span>  
 <span data-ttu-id="ade72-133">Exibe a SKU (unidade de manutenção de estoque), às vezes chamada de edição do produto.</span><span class="sxs-lookup"><span data-stu-id="ade72-133">Displays the product stock keeping unit (SKU), sometimes called the product edition.</span></span>  
  
 <span data-ttu-id="ade72-134">**Parâmetros de inicialização**</span><span class="sxs-lookup"><span data-stu-id="ade72-134">**Startup Parameters**</span></span>  
 <span data-ttu-id="ade72-135">Lista quaisquer parâmetroa usados por esta instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ade72-135">Lists any startup parameters that are used by this instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="ade72-136">Os parâmetros são separados por ponto-e-vírgulas.</span><span class="sxs-lookup"><span data-stu-id="ade72-136">Parameters are separated by semi-colons.</span></span> <span data-ttu-id="ade72-137">Entre os parâmetros padrão encontram-se os caminhos do arquivo de dados do banco de dados mestre (`master.mdf`), do arquivo de log do banco de dados mestre (`mastlog.ldf`), e do arquivo do log de erros.</span><span class="sxs-lookup"><span data-stu-id="ade72-137">The default parameters include the paths to the data file for the master database (`master.mdf`), the log file for the master database (`mastlog.ldf`), and the error log file.</span></span> <span data-ttu-id="ade72-138">Para obter a sintaxe dos parâmetros de inicialização, pesquise o tópico **Usando as opções de inicialização do serviço do SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="ade72-138">For the syntax of startup parameters, search Books Online for the topic **Using the SQL Server Service Startup Options.**</span></span>  
  
 <span data-ttu-id="ade72-139">**Unidade de Manutenção de Estoque**</span><span class="sxs-lookup"><span data-stu-id="ade72-139">**Stock Keeping Unit**</span></span>  
 <span data-ttu-id="ade72-140">Exibe o número da SKU (unidade de manutenção de estoque) do produto.</span><span class="sxs-lookup"><span data-stu-id="ade72-140">Displays the product stock keeping unit (SKU) number.</span></span>  
  
 <span data-ttu-id="ade72-141">**Versão**</span><span class="sxs-lookup"><span data-stu-id="ade72-141">**Version**</span></span>  
 <span data-ttu-id="ade72-142">Exibe o número de versão desta instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ade72-142">Displays the version number of this instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="ade72-143">**Nome do Servidor Virtual**</span><span class="sxs-lookup"><span data-stu-id="ade72-143">**Virtual Server Name**</span></span>  
 <span data-ttu-id="ade72-144">**Nome do Servidor Virtual** quando o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] é instalado em um servidor com cluster.</span><span class="sxs-lookup"><span data-stu-id="ade72-144">**Virtual Server Name** when [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is installed on a clustered server.</span></span>  
  
  
