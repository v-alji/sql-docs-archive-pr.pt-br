---
title: Editor de destino SQL (página avançado) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.sqlserverdestadapter.advanced.f1
helpviewer_keywords:
- SQL Server Destination Editor
ms.assetid: 9b46bcf8-ddaf-4d7d-90a6-80bc19517e9b
author: chugugrace
ms.author: chugu
ms.openlocfilehash: ccf25ad888c93f694678a152417affe5c0e16091
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87570755"
---
# <a name="sql-destination-editor-advanced-page"></a><span data-ttu-id="e93cf-102">Editor de Destino SQL (página Avançado)</span><span class="sxs-lookup"><span data-stu-id="e93cf-102">SQL Destination Editor (Advanced Page)</span></span>
  <span data-ttu-id="e93cf-103">Use a página **Avançado** da caixa de diálogo **Editor de Destino SQL** para especificar opções avançadas de inserção em massa.</span><span class="sxs-lookup"><span data-stu-id="e93cf-103">Use the **Advanced** page of the **SQL Destination Editor** dialog box to specify advanced bulk insert options.</span></span>  
  
 <span data-ttu-id="e93cf-104">Para obter mais informações sobre destino do SQL Server, consulte [SQL Server Destination](data-flow/sql-server-destination.md).</span><span class="sxs-lookup"><span data-stu-id="e93cf-104">To learn more about the SQL Server destination, see [SQL Server Destination](data-flow/sql-server-destination.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="e93cf-105">Opções</span><span class="sxs-lookup"><span data-stu-id="e93cf-105">Options</span></span>  
 <span data-ttu-id="e93cf-106">**Manter identidade**</span><span class="sxs-lookup"><span data-stu-id="e93cf-106">**Keep identity**</span></span>  
 <span data-ttu-id="e93cf-107">Especifique se a tarefa deve inserir valores em colunas de identidade.</span><span class="sxs-lookup"><span data-stu-id="e93cf-107">Specify whether the task should insert values into identity columns.</span></span> <span data-ttu-id="e93cf-108">O valor padrão dessa propriedade é `False`.</span><span class="sxs-lookup"><span data-stu-id="e93cf-108">The default value of this property is `False`.</span></span>  
  
 <span data-ttu-id="e93cf-109">**Manter nulos**</span><span class="sxs-lookup"><span data-stu-id="e93cf-109">**Keep nulls**</span></span>  
 <span data-ttu-id="e93cf-110">Especifique se a tarefa deve manter valores nulos.</span><span class="sxs-lookup"><span data-stu-id="e93cf-110">Specify whether the task should keep null values.</span></span> <span data-ttu-id="e93cf-111">O valor padrão dessa propriedade é `False`.</span><span class="sxs-lookup"><span data-stu-id="e93cf-111">The default value of this property is `False`.</span></span>  
  
 <span data-ttu-id="e93cf-112">**Bloqueio de tabela**</span><span class="sxs-lookup"><span data-stu-id="e93cf-112">**Table lock**</span></span>  
 <span data-ttu-id="e93cf-113">Especifique se a tabela deve ser bloqueada no carregamento de dados.</span><span class="sxs-lookup"><span data-stu-id="e93cf-113">Specify whether the table is locked when the data is loaded.</span></span> <span data-ttu-id="e93cf-114">O valor padrão dessa propriedade é `True`.</span><span class="sxs-lookup"><span data-stu-id="e93cf-114">The default value of this property is `True`.</span></span>  
  
 <span data-ttu-id="e93cf-115">**Verificar restrições**</span><span class="sxs-lookup"><span data-stu-id="e93cf-115">**Check constraints**</span></span>  
 <span data-ttu-id="e93cf-116">Especifique se a tarefa deve verificar restrições.</span><span class="sxs-lookup"><span data-stu-id="e93cf-116">Specify whether the task should check constraints.</span></span> <span data-ttu-id="e93cf-117">O valor padrão dessa propriedade é `True`.</span><span class="sxs-lookup"><span data-stu-id="e93cf-117">The default value of this property is `True`.</span></span>  
  
 <span data-ttu-id="e93cf-118">**Acionadores**</span><span class="sxs-lookup"><span data-stu-id="e93cf-118">**Fire triggers**</span></span>  
 <span data-ttu-id="e93cf-119">Especifique se a inserção em massa deve ativar gatilhos em tabelas.</span><span class="sxs-lookup"><span data-stu-id="e93cf-119">Specify whether the bulk insert should fire triggers on tables.</span></span> <span data-ttu-id="e93cf-120">O valor padrão dessa propriedade é `False`.</span><span class="sxs-lookup"><span data-stu-id="e93cf-120">The default value of this property is `False`.</span></span>  
  
 <span data-ttu-id="e93cf-121">**Primeira Linha**</span><span class="sxs-lookup"><span data-stu-id="e93cf-121">**First Row**</span></span>  
 <span data-ttu-id="e93cf-122">Especifique a primeira linha a inserir.</span><span class="sxs-lookup"><span data-stu-id="e93cf-122">Specify the first row to insert.</span></span> <span data-ttu-id="e93cf-123">O valor padrão desta propriedade é **-1**, indicando que nenhum valor foi atribuído.</span><span class="sxs-lookup"><span data-stu-id="e93cf-123">The default value of this property is **-1**, indicating that no value has been assigned.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e93cf-124">Limpe a caixa de texto no **Editor de Destino SQL** para indicar que não deseja atribuir um valor para esta propriedade.</span><span class="sxs-lookup"><span data-stu-id="e93cf-124">Clear the text box in the **SQL Destination Editor** to indicate that you do not want to assign a value for this property.</span></span> <span data-ttu-id="e93cf-125">Use -1 na janela **Propriedades** , no **Editor Avançado**e no modelo de objeto.</span><span class="sxs-lookup"><span data-stu-id="e93cf-125">Use -1 in the **Properties** window, the **Advanced Editor**, and the object model.</span></span>  
  
 <span data-ttu-id="e93cf-126">**Última Linha**</span><span class="sxs-lookup"><span data-stu-id="e93cf-126">**Last Row**</span></span>  
 <span data-ttu-id="e93cf-127">Especifique a última linha a inserir.</span><span class="sxs-lookup"><span data-stu-id="e93cf-127">Specify the last row to insert.</span></span> <span data-ttu-id="e93cf-128">O valor padrão desta propriedade é **-1**, indicando que nenhum valor foi atribuído.</span><span class="sxs-lookup"><span data-stu-id="e93cf-128">The default value of this property is **-1**, indicating that no value has been assigned.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e93cf-129">Limpe a caixa de texto no **Editor de Destino SQL** para indicar que não deseja atribuir um valor para esta propriedade.</span><span class="sxs-lookup"><span data-stu-id="e93cf-129">Clear the text box in the **SQL Destination Editor** to indicate that you do not want to assign a value for this property.</span></span> <span data-ttu-id="e93cf-130">Use -1 na janela **Propriedades** , no **Editor Avançado**e no modelo de objeto.</span><span class="sxs-lookup"><span data-stu-id="e93cf-130">Use -1 in the **Properties** window, the **Advanced Editor**, and the object model.</span></span>  
  
 <span data-ttu-id="e93cf-131">**Número máximo de erros**</span><span class="sxs-lookup"><span data-stu-id="e93cf-131">**Maximum number of errors**</span></span>  
 <span data-ttu-id="e93cf-132">Especifique o número máximo de erros permitido antes que a inserção em massa cesse.</span><span class="sxs-lookup"><span data-stu-id="e93cf-132">Specify the number of errors that can occur before the bulk insert stops.</span></span> <span data-ttu-id="e93cf-133">O valor padrão desta propriedade é **-1**, indicando que nenhum valor foi atribuído.</span><span class="sxs-lookup"><span data-stu-id="e93cf-133">The default value of this property is **-1**, indicating that no value has been assigned.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e93cf-134">Limpe a caixa de texto no **Editor de Destino SQL** para indicar que não deseja atribuir um valor para esta propriedade.</span><span class="sxs-lookup"><span data-stu-id="e93cf-134">Clear the text box in the **SQL Destination Editor** to indicate that you do not want to assign a value for this property.</span></span> <span data-ttu-id="e93cf-135">Use -1 na janela **Propriedades** , no **Editor Avançado**e no modelo de objeto.</span><span class="sxs-lookup"><span data-stu-id="e93cf-135">Use -1 in the **Properties** window, the **Advanced Editor**, and the object model.</span></span>  
  
 <span data-ttu-id="e93cf-136">**Tempo Limite**</span><span class="sxs-lookup"><span data-stu-id="e93cf-136">**Timeout**</span></span>  
 <span data-ttu-id="e93cf-137">Especifique o tempo limite, em segundos, a ser aguardado antes de interrupção da inserção em massa.</span><span class="sxs-lookup"><span data-stu-id="e93cf-137">Specify the number of seconds to wait before the bulk insert stops because of a time-out.</span></span>  
  
 <span data-ttu-id="e93cf-138">**Ordenar colunas**</span><span class="sxs-lookup"><span data-stu-id="e93cf-138">**Order columns**</span></span>  
 <span data-ttu-id="e93cf-139">Digite os nomes das colunas de classificação.</span><span class="sxs-lookup"><span data-stu-id="e93cf-139">Type the names of the sort columns.</span></span> <span data-ttu-id="e93cf-140">Cada coluna pode ser classificada em ordem crescente ou decrescente.</span><span class="sxs-lookup"><span data-stu-id="e93cf-140">Each column can be sorted in ascending or descending order.</span></span> <span data-ttu-id="e93cf-141">Ao usar várias colunas de classificação, delimite a lista com vírgulas.</span><span class="sxs-lookup"><span data-stu-id="e93cf-141">If you use multiple sort columns, delimit the list with commas.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e93cf-142">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="e93cf-142">See Also</span></span>  
 <span data-ttu-id="e93cf-143">[Referência de mensagens e erros do Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="e93cf-143">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="e93cf-144">[Editor de destinos SQL &#40;página Gerenciador de conexões&#41;](../../2014/integration-services/sql-destination-editor-connection-manager-page.md) </span><span class="sxs-lookup"><span data-stu-id="e93cf-144">[SQL Destination Editor &#40;Connection Manager Page&#41;](../../2014/integration-services/sql-destination-editor-connection-manager-page.md) </span></span>  
 <span data-ttu-id="e93cf-145">[Página Mapeamentos de &#40;do editor de destinos SQL&#41;](../../2014/integration-services/sql-destination-editor-mappings-page.md) </span><span class="sxs-lookup"><span data-stu-id="e93cf-145">[SQL Destination Editor &#40;Mappings Page&#41;](../../2014/integration-services/sql-destination-editor-mappings-page.md) </span></span>  
 [<span data-ttu-id="e93cf-146">Carregar dados em massa por meio do destino do SQL Server</span><span class="sxs-lookup"><span data-stu-id="e93cf-146">Bulk Load Data by Using the SQL Server Destination</span></span>](data-flow/bulk-load-data-by-using-the-sql-server-destination.md)  
  
  
