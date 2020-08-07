---
title: Gerenciar modelos (SQL Server suplementos de mineração de dados) | Microsoft Docs
ms.custom: ''
ms.date: 12/29/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- mining models, importing
- mining models, deleting
- mining models, managing
- mining models, training
- mining models, processing
- mining models, exporting
ms.assetid: c11380f0-7c24-4668-9cdf-9c53e4aff665
author: minewiskan
ms.author: owend
ms.openlocfilehash: 5f4b5961ec79bb949bf7fa5f53a980f066e81379
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87581579"
---
# <a name="manage-models-sql-server-data-mining-add-ins"></a><span data-ttu-id="5cea5-102">Gerenciar Modelos (Suplementos de Mineração de Dados do SQL Server)</span><span class="sxs-lookup"><span data-stu-id="5cea5-102">Manage Models (SQL Server Data Mining Add-ins)</span></span>
  <span data-ttu-id="5cea5-103">![Botão Gerenciar Modelos, faixa de opções Mineração de Dados](media/dmc-manage.gif "Botão Gerenciar Modelos, faixa de opções Mineração de Dados")</span><span class="sxs-lookup"><span data-stu-id="5cea5-103">![Manage Models button, Data Mining ribbon](media/dmc-manage.gif "Manage Models button, Data Mining ribbon")</span></span>  
  
 <span data-ttu-id="5cea5-104">A caixa de diálogo **gerenciar modelos** permite interagir com modelos de mineração e estruturas de mineração existentes que são armazenados no [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] servidor ao qual você está conectado no momento.</span><span class="sxs-lookup"><span data-stu-id="5cea5-104">The **Manage Models** dialog box enables you to interact with existing mining models and mining structures that are stored in the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] server to which you are currently connected.</span></span> <span data-ttu-id="5cea5-105">Também é possível exibir e gerenciar estruturas e modelos temporários criados durante a sessão atual.</span><span class="sxs-lookup"><span data-stu-id="5cea5-105">You can also view and manage temporary structures and models that have been created during the current session.</span></span> <span data-ttu-id="5cea5-106">Caso você tenha usado modelos de sessão e modelos armazenados em um servidor, os dois tipos estarão visíveis na caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="5cea5-106">If you have used both session models and models stored on a server, both are visible in the dialog box.</span></span>  
  
## <a name="using-the-manage-models-wizard"></a><span data-ttu-id="5cea5-107">Usando o Assistente para Gerenciar Modelos</span><span class="sxs-lookup"><span data-stu-id="5cea5-107">Using the Manage Models Wizard</span></span>  
 <span data-ttu-id="5cea5-108">Quando você clica em **gerenciar modelos**, a caixa de diálogo **gerenciar estruturas e modelos de mineração** é aberta, fornecendo acesso à seguinte funcionalidade para gerenciar modelos e estruturas existentes do Data Mining:</span><span class="sxs-lookup"><span data-stu-id="5cea5-108">When you click **Manage Models**, the **Manage Mining Structures and Models** dialog box opens, providing access to the following functionality for managing existing data mining models and structures:</span></span>  
  
-   <span data-ttu-id="5cea5-109">Renomear um modelo ou uma estrutura de mineração</span><span class="sxs-lookup"><span data-stu-id="5cea5-109">Rename a mining model or structure</span></span>  
  
-   <span data-ttu-id="5cea5-110">Excluir um modelo ou uma estrutura de mineração</span><span class="sxs-lookup"><span data-stu-id="5cea5-110">Delete a mining model or structure</span></span>  
  
-   <span data-ttu-id="5cea5-111">Limpar um modelo ou uma estrutura de mineração</span><span class="sxs-lookup"><span data-stu-id="5cea5-111">Clear a mining model or structure</span></span>  
  
-   <span data-ttu-id="5cea5-112">Processar uma estrutura de mineração, usando dados novos ou existentes</span><span class="sxs-lookup"><span data-stu-id="5cea5-112">Process a mining structure, using either new or existing data</span></span>  
  
-   <span data-ttu-id="5cea5-113">Exportar ou importar um modelo ou uma estrutura de mineração</span><span class="sxs-lookup"><span data-stu-id="5cea5-113">Export or import a mining model or structure</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5cea5-114">Não é possível criar consultas ou modelos usando essa caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="5cea5-114">You cannot create queries or models by using this dialog box.</span></span> <span data-ttu-id="5cea5-115">Para criar uma nova estrutura de mineração, use um dos assistentes fornecidos no cliente de mineração de dados para Excel ou use a **Editor avançado de consulta de mineração de dados**.</span><span class="sxs-lookup"><span data-stu-id="5cea5-115">To create a new mining structure, use one of the wizards provided in the Data Mining Client for Excel, or use the **Data Mining Query Advanced Editor**.</span></span>  
  
### <a name="requirements"></a><span data-ttu-id="5cea5-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5cea5-116">Requirements</span></span>  
 <span data-ttu-id="5cea5-117">Para gerenciar modelos de mineração de dados, primeiro você deve ter uma conexão com uma instância do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5cea5-117">To manage data mining models, you must first create a connection to an instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span></span> <span data-ttu-id="5cea5-118">Uma conexão será necessária mesmo que você esteja trabalhando com modelos de sessão armazenados em um arquivo temporário.</span><span class="sxs-lookup"><span data-stu-id="5cea5-118">A connection is required even if you are working with session models stored in a temporary file.</span></span> <span data-ttu-id="5cea5-119">Para obter mais informações sobre como criar ou alterar uma conexão, consulte [conectar-se a dados de origem &#40;cliente de mineração de dados para Excel&#41;](connect-to-source-data-data-mining-client-for-excel.md).</span><span class="sxs-lookup"><span data-stu-id="5cea5-119">For more information about how to create or change a connection, see [Connect to Source Data &#40;Data Mining Client for Excel&#41;](connect-to-source-data-data-mining-client-for-excel.md).</span></span>  
  
 <span data-ttu-id="5cea5-120">Se a instância do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] à qual você está conectado não contiver estruturas ou modelos de mineração de dados existentes, crie esses itens usando os assistentes e outras ferramentas fornecidas por este suplemento.</span><span class="sxs-lookup"><span data-stu-id="5cea5-120">If the instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] that you connect to does not contain any existing data mining structures or data mining models, you can create them by using the wizards and other tools provided by this add-in.</span></span> <span data-ttu-id="5cea5-121">Você também pode criar novos modelos usando o **modelo de mineração de dados editor avançado**.</span><span class="sxs-lookup"><span data-stu-id="5cea5-121">You can also create new models by using the **Data Mining Model Advanced Editor**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5cea5-122">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="5cea5-122">See Also</span></span>  
 <span data-ttu-id="5cea5-123">[Documentando modelos de mineração &#40;suplementos de mineração de dados para Excel&#41;](documenting-mining-models-data-mining-add-ins-for-excel.md) </span><span class="sxs-lookup"><span data-stu-id="5cea5-123">[Documenting Mining Models &#40;Data Mining Add-ins for Excel&#41;](documenting-mining-models-data-mining-add-ins-for-excel.md) </span></span>  
 [<span data-ttu-id="5cea5-124">Implantando e dimensionando modelos de mineração &#40;suplementos de mineração de dados para Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="5cea5-124">Deploying and Scaling Mining Models &#40;Data Mining Add-ins for Excel&#41;</span></span>](deploying-and-scaling-mining-models-data-mining-add-ins-for-excel.md)   

  
