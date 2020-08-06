---
title: Editor da tarefa inserção em massa (página Opções) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.bulkinserttask.options.f1
helpviewer_keywords:
- Bulk Insert Task Editor
ms.assetid: b3702811-3eb8-4b28-9190-5ae7a1a7bb6f
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 1751d1e0ac01d5459a8c76e6a48626c2ad6deafd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684301"
---
# <a name="bulk-insert-task-editor-options-page"></a><span data-ttu-id="d4f51-102">Editor da Tarefa Inserção em Massa (página de Opções)</span><span class="sxs-lookup"><span data-stu-id="d4f51-102">Bulk Insert Task Editor (Options Page)</span></span>
  <span data-ttu-id="d4f51-103">Use a página **Opções** da caixa de diálogo **Editor da Tarefa Inserção em Massa** para definir as propriedades da operação de inserção em massa.</span><span class="sxs-lookup"><span data-stu-id="d4f51-103">Use the **Options** page of the **Bulk Insert Task Editor** dialog box to set properties for the bulk insert operation.</span></span> <span data-ttu-id="d4f51-104">A tarefa Bulk Insert copia uma grande quantidade de dados em uma exibição ou tabela do [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d4f51-104">The Bulk Insert task copies large amounts of data into a [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] table or view.</span></span>  
  
 <span data-ttu-id="d4f51-105">Para saber mais sobre como trabalhar com inserções em massa, consulte [Tarefa Inserção em Massa](control-flow/bulk-insert-task.md) e [BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="d4f51-105">To learn about working with bulk inserts, see [Bulk Insert Task](control-flow/bulk-insert-task.md) and [BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql).</span></span>  
  
## <a name="options"></a><span data-ttu-id="d4f51-106">Opções</span><span class="sxs-lookup"><span data-stu-id="d4f51-106">Options</span></span>  
 <span data-ttu-id="d4f51-107">**CodePage**</span><span class="sxs-lookup"><span data-stu-id="d4f51-107">**CodePage**</span></span>  
 <span data-ttu-id="d4f51-108">Especifique a página de código dos dados no arquivo de dados.</span><span class="sxs-lookup"><span data-stu-id="d4f51-108">Specify the code page of the data in the data file.</span></span>  
  
 <span data-ttu-id="d4f51-109">**DataFileType**</span><span class="sxs-lookup"><span data-stu-id="d4f51-109">**DataFileType**</span></span>  
 <span data-ttu-id="d4f51-110">Especifique o valor do tipo de dados a ser usado na operação de carregamento.</span><span class="sxs-lookup"><span data-stu-id="d4f51-110">Specify the data-type value to use in the load operation.</span></span>  
  
 <span data-ttu-id="d4f51-111">**BatchSize**</span><span class="sxs-lookup"><span data-stu-id="d4f51-111">**BatchSize**</span></span>  
 <span data-ttu-id="d4f51-112">Especifique o número de linhas em um lote.</span><span class="sxs-lookup"><span data-stu-id="d4f51-112">Specify the number of rows in a batch.</span></span> <span data-ttu-id="d4f51-113">O padrão é todo o arquivo de dados.</span><span class="sxs-lookup"><span data-stu-id="d4f51-113">The default is the entire data file.</span></span> <span data-ttu-id="d4f51-114">Se você definir **BatchSize** para zero, os dados serão carregados em um único lote.</span><span class="sxs-lookup"><span data-stu-id="d4f51-114">If you set **BatchSize** to zero, the data is loaded in a single batch.</span></span>  
  
 <span data-ttu-id="d4f51-115">**LastRow**</span><span class="sxs-lookup"><span data-stu-id="d4f51-115">**LastRow**</span></span>  
 <span data-ttu-id="d4f51-116">Especifique a última linha a ser copiada.</span><span class="sxs-lookup"><span data-stu-id="d4f51-116">Specify the last row to copy.</span></span>  
  
 <span data-ttu-id="d4f51-117">**FirstRow**</span><span class="sxs-lookup"><span data-stu-id="d4f51-117">**FirstRow**</span></span>  
 <span data-ttu-id="d4f51-118">Especifique a primeira linha da qual começar a copiar.</span><span class="sxs-lookup"><span data-stu-id="d4f51-118">Specify the first row from which to start copying.</span></span>  
  
 <span data-ttu-id="d4f51-119">**Opções**</span><span class="sxs-lookup"><span data-stu-id="d4f51-119">**Options**</span></span>  
 |<span data-ttu-id="d4f51-120">Termo</span><span class="sxs-lookup"><span data-stu-id="d4f51-120">Term</span></span>|<span data-ttu-id="d4f51-121">Definição</span><span class="sxs-lookup"><span data-stu-id="d4f51-121">Definition</span></span>|  
|----------|----------------|  
|<span data-ttu-id="d4f51-122">**Verificar restrições**</span><span class="sxs-lookup"><span data-stu-id="d4f51-122">**Check constraints**</span></span>|<span data-ttu-id="d4f51-123">Selecione para verificar as restrições de tabelas e colunas.</span><span class="sxs-lookup"><span data-stu-id="d4f51-123">Select to check the table and column constraints.</span></span>|  
|<span data-ttu-id="d4f51-124">**Manter nulos**</span><span class="sxs-lookup"><span data-stu-id="d4f51-124">**Keep nulls**</span></span>|<span data-ttu-id="d4f51-125">Selecione para reter valores nulos durante a operação de inserção em massa, em vez de inserir qualquer valor padrão para colunas vazias.</span><span class="sxs-lookup"><span data-stu-id="d4f51-125">Select to retain null values during the bulk insert operation, instead of inserting any default values for empty columns.</span></span>|  
|<span data-ttu-id="d4f51-126">**Habilitar inserção de identidade**</span><span class="sxs-lookup"><span data-stu-id="d4f51-126">**Enable identity insert**</span></span>|<span data-ttu-id="d4f51-127">Selecione para inserir valores existentes em uma coluna de identidade.</span><span class="sxs-lookup"><span data-stu-id="d4f51-127">Select to insert existing values into an identity column.</span></span>|  
|<span data-ttu-id="d4f51-128">**Bloqueio de tabela**</span><span class="sxs-lookup"><span data-stu-id="d4f51-128">**Table lock**</span></span>|<span data-ttu-id="d4f51-129">Selecione para bloquear a tabela durante a inserção em massa.</span><span class="sxs-lookup"><span data-stu-id="d4f51-129">Select to lock the table during the bulk insert.</span></span>|  
|<span data-ttu-id="d4f51-130">**Acionadores**</span><span class="sxs-lookup"><span data-stu-id="d4f51-130">**Fire triggers**</span></span>|<span data-ttu-id="d4f51-131">Selecione para acionar qualquer inserção, atualização ou exclusão de gatilhos na tabela.</span><span class="sxs-lookup"><span data-stu-id="d4f51-131">Select to fire any insert, update, or delete triggers on the table.</span></span>|  
  
 <span data-ttu-id="d4f51-132">**SortedData**</span><span class="sxs-lookup"><span data-stu-id="d4f51-132">**SortedData**</span></span>  
 <span data-ttu-id="d4f51-133">Especifique a cláusula ORDER BY na instrução de inserção em massa.</span><span class="sxs-lookup"><span data-stu-id="d4f51-133">Specify the ORDER BY clause in the bulk insert statement.</span></span> <span data-ttu-id="d4f51-134">O nome da coluna que você fornece deve ser uma coluna válida na tabela de destino.</span><span class="sxs-lookup"><span data-stu-id="d4f51-134">The column name that you supply must be a valid column in the destination table.</span></span> <span data-ttu-id="d4f51-135">O padrão é `false`.</span><span class="sxs-lookup"><span data-stu-id="d4f51-135">The default is `false`.</span></span> <span data-ttu-id="d4f51-136">Isto significa que os dados não são classificados por uma cláusula ORDER BY.</span><span class="sxs-lookup"><span data-stu-id="d4f51-136">This means that the data is not sorted by an ORDER BY clause.</span></span>  
  
 <span data-ttu-id="d4f51-137">**MaxErrors**</span><span class="sxs-lookup"><span data-stu-id="d4f51-137">**MaxErrors**</span></span>  
 <span data-ttu-id="d4f51-138">Especifique o número máximo de erros que podem ocorrer antes que a operação de inserção em massa seja cancelada.</span><span class="sxs-lookup"><span data-stu-id="d4f51-138">Specify the maximum number of errors that can occur before the bulk insert operation is canceled.</span></span> <span data-ttu-id="d4f51-139">Um valor de 0 indica que um número infinito de erros é permitido.</span><span class="sxs-lookup"><span data-stu-id="d4f51-139">A value of 0 indicates that an infinite number of errors are allowed.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d4f51-140">Cada linha que não pode ser importada pela operação de carregamento em massa é contada como um erro.</span><span class="sxs-lookup"><span data-stu-id="d4f51-140">Each row that cannot be imported by the bulk load operation is counted as one error.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d4f51-141">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="d4f51-141">See Also</span></span>  
 <span data-ttu-id="d4f51-142">[Referência de mensagens e erros do Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="d4f51-142">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="d4f51-143">[Editor da tarefa inserção em massa &#40;página Geral&#41;](general-page-of-integration-services-designers-options.md) </span><span class="sxs-lookup"><span data-stu-id="d4f51-143">[Bulk Insert Task Editor &#40;General Page&#41;](general-page-of-integration-services-designers-options.md) </span></span>  
 <span data-ttu-id="d4f51-144">[Editor da tarefa inserção em massa &#40;página conexão&#41;](../../2014/integration-services/bulk-insert-task-editor-connection-page.md) </span><span class="sxs-lookup"><span data-stu-id="d4f51-144">[Bulk Insert Task Editor &#40;Connection Page&#41;](../../2014/integration-services/bulk-insert-task-editor-connection-page.md) </span></span>  
 <span data-ttu-id="d4f51-145">[Página Expressões](expressions/expressions-page.md) </span><span class="sxs-lookup"><span data-stu-id="d4f51-145">[Expressions Page](expressions/expressions-page.md) </span></span>  
 [<span data-ttu-id="d4f51-146">Fluxo de Controle</span><span class="sxs-lookup"><span data-stu-id="d4f51-146">Control Flow</span></span>](control-flow/control-flow.md)  
  
  
