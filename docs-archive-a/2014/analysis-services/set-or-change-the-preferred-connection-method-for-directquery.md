---
title: Definir ou alterar o método de conexão preferencial para DirectQuery | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: f10d5678-d678-4251-8cce-4e30cfe15751
author: minewiskan
ms.author: owend
ms.openlocfilehash: 239c80ace0daa3498c8dafd8fea358ce540931d3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683722"
---
# <a name="set-or-change-the-preferred-connection-method-for-directquery"></a><span data-ttu-id="04753-102">Definir ou alterar o método de conexão preferencial para DirectQuery</span><span class="sxs-lookup"><span data-stu-id="04753-102">Set or Change the Preferred Connection Method for DirectQuery</span></span>
  <span data-ttu-id="04753-103">Quando você criar um modelo para uso em modo DirectQuery, primeiro configure o ambiente de design para oferece suporte ao uso do DirectQuery.</span><span class="sxs-lookup"><span data-stu-id="04753-103">When you create a model for use in DirectQuery mode, you must first configure the design environment to support use of DirectQuery.</span></span> <span data-ttu-id="04753-104">Para fazer isso, consulte [habilitar modo de design do DirectQuery &#40;SSAS de tabela&#41;](tabular-models/enable-directquery-mode-in-ssdt.md).</span><span class="sxs-lookup"><span data-stu-id="04753-104">To do this, see [Enable DirectQuery Design Mode &#40;SSAS Tabular&#41;](tabular-models/enable-directquery-mode-in-ssdt.md).</span></span>  
  
 <span data-ttu-id="04753-105">Quando você estiver pronto para implantar o modelo, defina algumas propriedades adicionais para habilitar usuários a acessar seu modelo usando um dos modos do DirectQuery:</span><span class="sxs-lookup"><span data-stu-id="04753-105">When you are ready to deploy the model, you must set some additional properties to enable users to access your model using one of the DirectQuery modes:</span></span>  
  
-   <span data-ttu-id="04753-106">Você precisa indicar se as consultas no modelo devem usar dados armazenados em cache ou a fonte de dados relacional.</span><span class="sxs-lookup"><span data-stu-id="04753-106">You must indicate whether queries against the model should use cached data or the relational data source.</span></span> <span data-ttu-id="04753-107">Você só pode usar um modo híbrido ou DirectQuery.</span><span class="sxs-lookup"><span data-stu-id="04753-107">You can use a hybrid mode or DirectQuery only.</span></span>  
  
-   <span data-ttu-id="04753-108">Se você estiver usando partições, indique a partição a ser usada como a fonte de dados do DirectQuery.</span><span class="sxs-lookup"><span data-stu-id="04753-108">If you are using partitions, you must indicate which partition to use as the DirectQuery data source.</span></span>  
  
-   <span data-ttu-id="04753-109">Você deve definir opções de representação para usuários que estarão acessando a fonte de dados do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="04753-109">You must set impersonation options for users who will be accessing the SQL Server data source.</span></span>  
  
 <span data-ttu-id="04753-110">Este procedimento descreve como definir o método de conexão preferencial para um modelo DirectQuery no designer.</span><span class="sxs-lookup"><span data-stu-id="04753-110">This procedure describes how to set the preferred connection method for a DirectQuery model in the designer.</span></span> <span data-ttu-id="04753-111">Ele também descreve como alterar esta propriedade no [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] depois da implantação do modelo.</span><span class="sxs-lookup"><span data-stu-id="04753-111">It also describes how you can change this property in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] after the model has been deployed.</span></span>  
  
### <a name="to-set-the-preferred-connection-method-for-a-directquery-model"></a><span data-ttu-id="04753-112">Para definir o método de conexão preferencial para um modelo DirectQuery</span><span class="sxs-lookup"><span data-stu-id="04753-112">To set the preferred connection method for a DirectQuery model</span></span>  
  
1.  <span data-ttu-id="04753-113">No [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], abra o arquivo de solução para o modelo DirectQuery.</span><span class="sxs-lookup"><span data-stu-id="04753-113">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the solution file for the DirectQuery model.</span></span>  
  
2.  <span data-ttu-id="04753-114">No Visual Studio, no menu **Projeto** , selecione **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="04753-114">In Visual Studio, from the **Project** menu, select **Properties**.</span></span>  
  
3.  <span data-ttu-id="04753-115">No painel **Propriedades** , altere a propriedade, **DirectQueryMode**, para um dos valores que oferecem suporte ao uso do DirectQuery:</span><span class="sxs-lookup"><span data-stu-id="04753-115">In the **Properties** pane, change the property, **DirectQueryMode**, to one of the values that support DirectQuery usage:</span></span>  
  
    -   <span data-ttu-id="04753-116">**InMemory com DirectQuery**: Se você usar esta opção, o modelo será implantado mas você deverá processar o cache antes de poder executar consultas no modelo.</span><span class="sxs-lookup"><span data-stu-id="04753-116">**InMemory with DirectQuery**: If you use this option, the model is deployed but you must process the cache before you can run queries against the model.</span></span>  
  
    -   <span data-ttu-id="04753-117">**DirectQuery com InMemory**: Se você usar esta opção, o cache estará disponível para uso por clientes se ele já tiver sido processado.</span><span class="sxs-lookup"><span data-stu-id="04753-117">**DirectQuery with InMemory**: If you use this option, the cache will be available for use by clients if it has already been processed.</span></span> <span data-ttu-id="04753-118">Se você implantar o modelo com esta configuração e não processar o cache, alguns clientes obterão um erro ao tentar se conectar ao modelo.</span><span class="sxs-lookup"><span data-stu-id="04753-118">If you deploy the model with this setting and do not process the cache, some clients must get an error on trying to connect to the model.</span></span>  
  
    -   <span data-ttu-id="04753-119">**somente DirectQuery**: Se você usar esta opção, os metadados serão implantados mas o modelo não conterá dados.</span><span class="sxs-lookup"><span data-stu-id="04753-119">**DirectQuery only**: If you use this option, the metadata is deployed but the model has no data in it.</span></span> <span data-ttu-id="04753-120">Clientes que tentam se conectar usando o modo Na memória obterão um erro, indicando que o modelo não existe ou não foi processado.</span><span class="sxs-lookup"><span data-stu-id="04753-120">Clients that attempt to connect using In-Memory mode will get an error, indicating that the model does not exist or has not been processed.</span></span>  
  
4.  <span data-ttu-id="04753-121">Se houver erros no Visual Studio, abra a **Lista de Erros** e resolva os problemas que possam impedir a implantação do modelo no modo DirectQuery.</span><span class="sxs-lookup"><span data-stu-id="04753-121">If there are errors, in Visual Studio, open the **Error List** and resolve any problems that would prevent the model from being deployed in DirectQuery mode.</span></span>  
  
### <a name="to-verify-or-change-the-preferred-connection-method-for-a-directquery-model"></a><span data-ttu-id="04753-122">Para verificar ou alterar o método de conexão preferencial para um modelo DirectQuery</span><span class="sxs-lookup"><span data-stu-id="04753-122">To verify or change the preferred connection method for a DirectQuery model</span></span>  
  
1.  <span data-ttu-id="04753-123">No [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], conecte-se à instância onde você implantou o modelo DirectQuery.</span><span class="sxs-lookup"><span data-stu-id="04753-123">In [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], connect to the instance where you deployed the DirectQuery model.</span></span>  
  
2.  <span data-ttu-id="04753-124">Clique com o botão direito do mouse no banco de dados modelo e selecione **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="04753-124">Right-click the model database, and select **Properties**.</span></span>  
  
3.  <span data-ttu-id="04753-125">No painel **Propriedades** , altere a propriedade **DirectQueryMode**para um destes valores:</span><span class="sxs-lookup"><span data-stu-id="04753-125">In the **Properties** pane, change the property, **DirectQueryMode**, to one of these values:</span></span>  
  
    -   <span data-ttu-id="04753-126">**Somente DirectQuery**</span><span class="sxs-lookup"><span data-stu-id="04753-126">**DirectQuery Only**</span></span>  
  
    -   <span data-ttu-id="04753-127">**InMemory com DirectQuery**</span><span class="sxs-lookup"><span data-stu-id="04753-127">**InMemory with DirectQuery**</span></span>  
  
    -   <span data-ttu-id="04753-128">**DirectQuery com inmemory**</span><span class="sxs-lookup"><span data-stu-id="04753-128">**DirectQuery with InMemory**</span></span>  
  
 <span data-ttu-id="04753-129">Observe que estas propriedades são iguais às propriedades que você define no projeto antes da implantação no Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="04753-129">Note that these properties are the same as the properties that you set on the project before deployment in Visual Studio.</span></span> <span data-ttu-id="04753-130">Você pode alterar o modo de conexão preferencial a qualquer momento para o modo DirectQuery, desde que o modelo esteja configurado para oferecer suporte ao uso do DirectQuery.</span><span class="sxs-lookup"><span data-stu-id="04753-130">You can change the preferred connection mode for DirectQuery mode at any time, provided that you have configured the model to support DirectQuery usage.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04753-131">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="04753-131">See Also</span></span>  
 <span data-ttu-id="04753-132">[Modo DirectQuery &#40;SSAS de tabela&#41;](tabular-models/directquery-mode-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="04753-132">[DirectQuery Mode &#40;SSAS Tabular&#41;](tabular-models/directquery-mode-ssas-tabular.md) </span></span>  
 [<span data-ttu-id="04753-133">Habilitar modo de design do DirectQuery &#40;SSAS de tabela&#41;</span><span class="sxs-lookup"><span data-stu-id="04753-133">Enable DirectQuery Design Mode &#40;SSAS Tabular&#41;</span></span>](tabular-models/enable-directquery-mode-in-ssdt.md)  
  
  
