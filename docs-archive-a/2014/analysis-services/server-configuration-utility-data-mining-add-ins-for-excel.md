---
title: Utilitário de configuração do servidor (suplementos de mineração de dados para Excel) | Microsoft Docs
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 28435f86-5cec-4a1e-9b7d-b2069c1ddddb
author: minewiskan
ms.author: owend
ms.openlocfilehash: f985338e44bf0f4b591fcb70a4e093901626149f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87686401"
---
# <a name="server-configuration-utility-data-mining-add-ins-for-excel"></a><span data-ttu-id="e17d7-102">Utilitário de Configuração de Servidor (Suplementos de Mineração de Dados para Excel)</span><span class="sxs-lookup"><span data-stu-id="e17d7-102">Server Configuration Utility (Data Mining Add-ins for Excel)</span></span>
  <span data-ttu-id="e17d7-103">Quando você instala os suplementos de mineração de dados para Excel, um utilitário de configuração do servidor também é instalado e será executado na primeira vez que você abrir os suplementos. Este tópico descreve como usar o utilitário para se conectar a uma instância do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] e configurar um banco de dados para trabalhar com modelos de data mining.</span><span class="sxs-lookup"><span data-stu-id="e17d7-103">When you install the Data Mining Add-ins for Excel, a Server Configuration Utility is also installed, and will run the first time you open the add-ins. This topic describes how to use the utility to connect to an instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] and set up a database for working with data mining models.</span></span>  
  

  
##  <a name="step-1-connect-to-analysis-services"></a><a name="bkmk_step1"></a><span data-ttu-id="e17d7-104">Etapa 1: conectar-se ao Analysis Services</span><span class="sxs-lookup"><span data-stu-id="e17d7-104">Step 1: Connect to Analysis Services</span></span>  
 <span data-ttu-id="e17d7-105">Escolha o servidor do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] que fornece os algoritmos de mineração de dados e armazena os modelos de mineração de dados.</span><span class="sxs-lookup"><span data-stu-id="e17d7-105">Choose the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] server that provides the data mining algorithms and stores your data mining models.</span></span>  
  
 <span data-ttu-id="e17d7-106">Quando você cria uma conexão para permitir a mineração de dados, é necessário escolher um servidor onde seja possível fazer experiências com modelos de mineração de dados.</span><span class="sxs-lookup"><span data-stu-id="e17d7-106">When you create a connection to enable data mining, you should choose a server where you can experiment with data mining models.</span></span> <span data-ttu-id="e17d7-107">Recomendamos que você crie um novo banco de dados do servidor e dedique o novo banco de dados da mineração de dados ou peça ao administrador para preparar um servidor de mineração de dados.</span><span class="sxs-lookup"><span data-stu-id="e17d7-107">We recommend that you create a new database on the server and dedicate the new database to data mining, or ask your administrator to prepare a data mining server for you.</span></span> <span data-ttu-id="e17d7-108">Dessa forma, você pode criar modelos sem afetar o desempenho de outros serviços.</span><span class="sxs-lookup"><span data-stu-id="e17d7-108">That way you can build models without affecting the performance of other services.</span></span>  
  
 <span data-ttu-id="e17d7-109">Observe que o servidor do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] que você usa para mineração de dados não precisa estar no mesmo servidor da fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="e17d7-109">Note that the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] server that you use for data mining does not need to be on the same server as your source data.</span></span>  
  
 <span data-ttu-id="e17d7-110">**Nome do servidor**</span><span class="sxs-lookup"><span data-stu-id="e17d7-110">**Server name**</span></span>  
 <span data-ttu-id="e17d7-111">Digite o nome do servidor que contém a instância do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] que você usará para mineração de dados.</span><span class="sxs-lookup"><span data-stu-id="e17d7-111">Type the name of the server that contains the instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] that you will use for data mining.</span></span>  
  
 <span data-ttu-id="e17d7-112">**Autenticação**</span><span class="sxs-lookup"><span data-stu-id="e17d7-112">**Authentication**</span></span>  
 <span data-ttu-id="e17d7-113">Especifique os métodos de autenticação.</span><span class="sxs-lookup"><span data-stu-id="e17d7-113">Specify the authentication methods.</span></span> <span data-ttu-id="e17d7-114">A Autenticação do Windows é necessária para conexões com o [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], a menos que o administrador tenha configurado o acesso ao servidor por meio de HTTPPump.</span><span class="sxs-lookup"><span data-stu-id="e17d7-114">Windows Authentication is required for connections to [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], unless your administrator has configured access to the server via the HTTPPump.</span></span>  
  
##  <a name="step-2-allow-temporary-models"></a><a name="bkmk_step2"></a><span data-ttu-id="e17d7-115">Etapa 2: permitir modelos temporários</span><span class="sxs-lookup"><span data-stu-id="e17d7-115">Step 2: Allow Temporary Models</span></span>  
 <span data-ttu-id="e17d7-116">Antes de poder usar os suplementos, uma propriedade de servidor do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] deve ser alterada para permitir a criação de modelos de mineração temporários.</span><span class="sxs-lookup"><span data-stu-id="e17d7-116">Before you can use the add-ins, an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] server property must be changed to permit the creation of temporary mining models.</span></span>  
  
 <span data-ttu-id="e17d7-117">Os modelos de mineração temporários também são chamados de *modelos de sessão*.</span><span class="sxs-lookup"><span data-stu-id="e17d7-117">Temporary mining models are also called *session models*.</span></span> <span data-ttu-id="e17d7-118">Isso ocorre porque os modelos são armazenados apenas enquanto a sessão atual permanece aberta.</span><span class="sxs-lookup"><span data-stu-id="e17d7-118">This is because the models are stored only as long as your current session is open.</span></span> <span data-ttu-id="e17d7-119">Quando você fecha a conexão com o servidor, a sessão é encerrada e os modelos usados durante ela são excluídos.</span><span class="sxs-lookup"><span data-stu-id="e17d7-119">When you close your connection to the server, the session is ended and any models used during the session are deleted.</span></span>  
  
 <span data-ttu-id="e17d7-120">O uso de modelos de mineração de sessão não afeta o espaço de armazenamento no servidor, mas a sobrecarga envolvida na criação de modelos de mineração de dados pode afetar o desempenho do servidor.</span><span class="sxs-lookup"><span data-stu-id="e17d7-120">The use of session mining models does not affect storage space on the server, but the overhead involved in creating data mining models may affect the performance of the server.</span></span>  
  
 <span data-ttu-id="e17d7-121">O assistente detecta primeiro as configurações no servidor que você especificou.</span><span class="sxs-lookup"><span data-stu-id="e17d7-121">The wizard first detects the settings on the server that you specified.</span></span> <span data-ttu-id="e17d7-122">Se o servidor já permitir modelos de mineração temporários, você poderá clicar em **Avançar** para continuar.</span><span class="sxs-lookup"><span data-stu-id="e17d7-122">If the server already allows temporary mining models, you can click **Next** to continue.</span></span> <span data-ttu-id="e17d7-123">O assistente também fornece instruções sobre como habilitar modelos de mineração temporários no servidor especificado do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] ou como fazer uma solicitação ao administrador do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e17d7-123">The wizard also provides instructions for how to enable temporary mining models on the specified [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] server, or how to make a request to your [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] administrator.</span></span>  
  
##  <a name="step-3-create-database-for-add-in-users"></a><a name="bkmk_step3"></a><span data-ttu-id="e17d7-124">Etapa 3: criar um banco de dados para usuários do suplemento</span><span class="sxs-lookup"><span data-stu-id="e17d7-124">Step 3: Create Database for Add-in Users</span></span>  
 <span data-ttu-id="e17d7-125">Nesta página do assistente de instalação e configuração, você pode criar um novo banco de dados dedicado à mineração de dados ou selecionar um banco de dados [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] existente.</span><span class="sxs-lookup"><span data-stu-id="e17d7-125">On this page of the setup and configuration wizard, you can create a new database that is dedicated to data mining, or select an existing [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database.</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="e17d7-126">A mineração de dados requer uma instância do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] em execução no modo multidimensional.</span><span class="sxs-lookup"><span data-stu-id="e17d7-126">Data mining requires an instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] that is running in multidimensional mode.</span></span> <span data-ttu-id="e17d7-127">O modo de tabela não oferece suporte à mineração de dados.</span><span class="sxs-lookup"><span data-stu-id="e17d7-127">Tabular mode does not support data mining.</span></span>  
  
 <span data-ttu-id="e17d7-128">É recomendável criar um banco de dados separado dedicado à mineração de dados.</span><span class="sxs-lookup"><span data-stu-id="e17d7-128">We recommend that you create a separate database dedicated to data mining.</span></span> <span data-ttu-id="e17d7-129">Isso lhe permite fazer experiências com modelos de mineração de dados sem afetar outros objetos da solução.</span><span class="sxs-lookup"><span data-stu-id="e17d7-129">This lets you experiment with data mining models without affecting other solution objects.</span></span>  
  
 <span data-ttu-id="e17d7-130">Se você escolher um banco de dados existente em uma instância do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], observe que será possível substituir modelos existentes se você usar os suplementos para criar um modelo e já houver um modelo com esse nome.</span><span class="sxs-lookup"><span data-stu-id="e17d7-130">If you choose an existing database on an instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], note that it is possible to overwrite existing models if you use the add-ins to create a model and a model of that name already exists.</span></span>  
  
 <span data-ttu-id="e17d7-131">**Criar novo banco de dados**</span><span class="sxs-lookup"><span data-stu-id="e17d7-131">**Create new database**</span></span>  
 <span data-ttu-id="e17d7-132">Selecione esta opção para criar um novo banco de dados no servidor selecionado.</span><span class="sxs-lookup"><span data-stu-id="e17d7-132">Select this option to create a new database on the selected server.</span></span> <span data-ttu-id="e17d7-133">Um banco de dados de mineração de dados armazenará suas fontes de dados, estruturas de mineração e modelos de mineração.</span><span class="sxs-lookup"><span data-stu-id="e17d7-133">A data mining database will store your data sources, mining structures, and mining models.</span></span>  
  
 <span data-ttu-id="e17d7-134">**Nome do banco de dados**</span><span class="sxs-lookup"><span data-stu-id="e17d7-134">**Database name**</span></span>  
 <span data-ttu-id="e17d7-135">Digite o nome do novo banco de dados.</span><span class="sxs-lookup"><span data-stu-id="e17d7-135">Type the name of the new database.</span></span> <span data-ttu-id="e17d7-136">Se o nome ainda não estiver em uso, ele será criado para você.</span><span class="sxs-lookup"><span data-stu-id="e17d7-136">If the name is not already in use, it will be created for you.</span></span>  
  
 <span data-ttu-id="e17d7-137">**Usar banco de dados existente**</span><span class="sxs-lookup"><span data-stu-id="e17d7-137">**Use existing database**</span></span>  
 <span data-ttu-id="e17d7-138">Selecione esta opção para usar um banco de dados [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] existente.</span><span class="sxs-lookup"><span data-stu-id="e17d7-138">Select this option to use an existing [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database.</span></span>  
  
 <span data-ttu-id="e17d7-139">**Backup de banco de dados**</span><span class="sxs-lookup"><span data-stu-id="e17d7-139">**Database**</span></span>  
 <span data-ttu-id="e17d7-140">Se você escolher a opção de usar um banco de dados existente, selecione o nome desse banco de dados na lista.</span><span class="sxs-lookup"><span data-stu-id="e17d7-140">If you chose the option to use an existing database, you must select the database name from the list.</span></span>  
  
##  <a name="step-4-give-add-in-users-appropriate-permissions"></a><a name="bkmk_step4"></a><span data-ttu-id="e17d7-141">Etapa 4: conceder permissões apropriadas aos usuários do suplemento</span><span class="sxs-lookup"><span data-stu-id="e17d7-141">Step 4: Give Add-in Users Appropriate Permissions</span></span>  
 <span data-ttu-id="e17d7-142">Você deve assegurar que você e outros usuários de suplementos tenham as permissões necessárias para procurar, editar, processar ou criar estruturas e modelos de mineração de dados.</span><span class="sxs-lookup"><span data-stu-id="e17d7-142">You must ensure that you (and any other users of the add-ins) have the necessary permissions to browse, edit, process, or create data mining structures and models.</span></span>  
  
 <span data-ttu-id="e17d7-143">Por padrão, a Autenticação do Windows integrada é necessária para uso dos suplementos.</span><span class="sxs-lookup"><span data-stu-id="e17d7-143">By default, integrated Windows Authentication is required to use the add-ins.</span></span>  
  
 <span data-ttu-id="e17d7-144">**Dar aos usuários de suplementos permissões de administração de banco de dados**</span><span class="sxs-lookup"><span data-stu-id="e17d7-144">**Give add-in users database administration permissions**</span></span>  
 <span data-ttu-id="e17d7-145">Selecione esta opção para dar aos usuários listados acesso administrativo ao banco de dados.</span><span class="sxs-lookup"><span data-stu-id="e17d7-145">Select this option to give the listed users administrative access to the database.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e17d7-146">Essas permissões se aplicam somente ao banco de dados listado na caixa **nome do banco de dados** .</span><span class="sxs-lookup"><span data-stu-id="e17d7-146">These permissions apply only to the database listed in the **Database name** box.</span></span>  
  
 <span data-ttu-id="e17d7-147">**Nome do banco de dados**</span><span class="sxs-lookup"><span data-stu-id="e17d7-147">**Database name**</span></span>  
 <span data-ttu-id="e17d7-148">Exibe o nome do banco de dados selecionado.</span><span class="sxs-lookup"><span data-stu-id="e17d7-148">Displays the name of the selected database.</span></span>  
  
 <span data-ttu-id="e17d7-149">**Especificar os usuários ou grupos a serem adicionados**</span><span class="sxs-lookup"><span data-stu-id="e17d7-149">**Specify users or groups to add**</span></span>  
 <span data-ttu-id="e17d7-150">Selecione os logons que terão acesso ao banco de dados usado para mineração de dados.</span><span class="sxs-lookup"><span data-stu-id="e17d7-150">Select the logins that will have access to the database used for data mining.</span></span>  
  
 <span data-ttu-id="e17d7-151">**Adicionar**</span><span class="sxs-lookup"><span data-stu-id="e17d7-151">**Add**</span></span>  
 <span data-ttu-id="e17d7-152">Clique para abrir uma caixa de diálogo e adicionar usuários ou grupos.</span><span class="sxs-lookup"><span data-stu-id="e17d7-152">Click to open a dialog box and add users or groups.</span></span>  
  
 <span data-ttu-id="e17d7-153">**Remover**</span><span class="sxs-lookup"><span data-stu-id="e17d7-153">**Remove**</span></span>  
 <span data-ttu-id="e17d7-154">Clique para remover o usuário ou grupo selecionado na lista de usuários com permissões administrativas.</span><span class="sxs-lookup"><span data-stu-id="e17d7-154">Click to remove the selected user or group from the list of users with administration permissions.</span></span>  
  
  
