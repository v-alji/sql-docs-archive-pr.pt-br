---
title: Visualizador de Conflitos de Replicação da Microsoft (replicação transacional) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.replconflictviewer.cvqueued.f1
ms.assetid: eec59d8e-cadb-4623-a31f-9f42ec09c97f
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 8cc3f2ea3d1d2b29fba9c9d9121e23bf4bcd88bd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87568484"
---
# <a name="microsoft-replication-conflict-viewer-transactional-replication"></a><span data-ttu-id="4f4d6-102">Visualizador de Conflitos de Replicação da Microsoft (replicação transacional)</span><span class="sxs-lookup"><span data-stu-id="4f4d6-102">Microsoft Replication Conflict Viewer (Transactional Replication)</span></span>
  <span data-ttu-id="4f4d6-103">O Visualizador de Conflitos de Replicação permite exibir conflitos que ocorreram durante a sincronização para uma replicação transacional ponto a ponto de uma replicação transacional com assinaturas de atualização enfileiradas.</span><span class="sxs-lookup"><span data-stu-id="4f4d6-103">The Replication Conflict Viewer enables you to view conflicts that have occurred during synchronization for peer-to-peer transactional replication and transactional replication with queued updating subscriptions.</span></span> <span data-ttu-id="4f4d6-104">Para obter mais informações, consulte [Exibir conflitos de dados em publicações transacionais &#40;SQL Server Management Studio&#41;](view-data-conflicts-for-transactional-publications-sql-server-management-studio.md).</span><span class="sxs-lookup"><span data-stu-id="4f4d6-104">For more information, see [View Data Conflicts for Transactional Publications &#40;SQL Server Management Studio&#41;](view-data-conflicts-for-transactional-publications-sql-server-management-studio.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4f4d6-105">O Visualizador de Conflitos de Replicação exibe conflitos que ocorrem em replicação de mesclagem e em replicação transacional.</span><span class="sxs-lookup"><span data-stu-id="4f4d6-105">The Replication Conflict Viewer displays conflicts that occur in merge replication and in transactional replication.</span></span> <span data-ttu-id="4f4d6-106">Para replicação transacional, você pode usar o Visualizador de Conflitos de Replicação para exibir dados de conflito, mas não pode escolher uma solução diferente para o conflito.</span><span class="sxs-lookup"><span data-stu-id="4f4d6-106">For transactional replication, you can use Replication Conflict Viewer to view conflict data, but you cannot choose a different resolution for the conflict.</span></span>  
  
## <a name="options"></a><span data-ttu-id="4f4d6-107">Opções</span><span class="sxs-lookup"><span data-stu-id="4f4d6-107">Options</span></span>  
 <span data-ttu-id="4f4d6-108">O Visualizador de Conflitos de Replicação é dividido em duas seções.</span><span class="sxs-lookup"><span data-stu-id="4f4d6-108">The Replication Conflict Viewer is divided into two sections.</span></span> <span data-ttu-id="4f4d6-109">A seção superior da caixa de diálogo mostra a lista de conflitos para a tabela selecionada.</span><span class="sxs-lookup"><span data-stu-id="4f4d6-109">The upper section of the dialog box shows the conflict list for the selected table.</span></span> <span data-ttu-id="4f4d6-110">Quando você clica em um item na lista de conflitos, os detalhes do conflito são exibidos na seção inferior da caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="4f4d6-110">When you click an item in the conflict list, the details of the conflict are displayed in the lower section of the dialog box.</span></span>  
  
 <span data-ttu-id="4f4d6-111">Os dados de conflito na seção inferior são exibidos em duas colunas correspondentes (**Vencedor do Conflito** e **Perdedor do Conflito**).</span><span class="sxs-lookup"><span data-stu-id="4f4d6-111">The conflict data in the lower section is displayed in two corresponding columns (**Conflict Winner** and **Conflict Loser**).</span></span> <span data-ttu-id="4f4d6-112">Se o conflito estiver entre os dados atualizados e excluídos, talvez não haja dados a serem exibidos no lado excluído do conflito.</span><span class="sxs-lookup"><span data-stu-id="4f4d6-112">If the conflict is between updated and deleted data, there may be no data to show for the deleted side of the conflict.</span></span> <span data-ttu-id="4f4d6-113">Nesse caso, o Visualizador de Conflitos de Replicação exibe uma mensagem em uma das colunas, indicando que a linha foi excluída em um local e atualizada em outro.</span><span class="sxs-lookup"><span data-stu-id="4f4d6-113">In this case, the Replication Conflict Viewer displays a message in one of the columns, indicating the row was deleted at one location and updated at another.</span></span> <span data-ttu-id="4f4d6-114">Também indica a resolução sugerida.</span><span class="sxs-lookup"><span data-stu-id="4f4d6-114">It also indicates the suggested resolution.</span></span>  
  
 <span data-ttu-id="4f4d6-115">**Backup de banco de dados**</span><span class="sxs-lookup"><span data-stu-id="4f4d6-115">**Database**</span></span>  
 <span data-ttu-id="4f4d6-116">Escolha um banco de dados que inclua publicações com conflitos.</span><span class="sxs-lookup"><span data-stu-id="4f4d6-116">Choose a database that includes publications with conflicts.</span></span>  
  
 <span data-ttu-id="4f4d6-117">**Publicação**</span><span class="sxs-lookup"><span data-stu-id="4f4d6-117">**Publication**</span></span>  
 <span data-ttu-id="4f4d6-118">Escolha uma publicação que inclua tabelas com conflitos.</span><span class="sxs-lookup"><span data-stu-id="4f4d6-118">Choose a publication that includes tables with conflicts.</span></span>  
  
 <span data-ttu-id="4f4d6-119">**Tabela**</span><span class="sxs-lookup"><span data-stu-id="4f4d6-119">**Table**</span></span>  
 <span data-ttu-id="4f4d6-120">Escolha uma tabela que inclua conflitos.</span><span class="sxs-lookup"><span data-stu-id="4f4d6-120">Choose a table that includes conflicts.</span></span>  
  
 <span data-ttu-id="4f4d6-121">**Definir Filtro**</span><span class="sxs-lookup"><span data-stu-id="4f4d6-121">**Define Filter**</span></span>  
 <span data-ttu-id="4f4d6-122">Clique para abrir a caixa de diálogo **Definir Filtros** .</span><span class="sxs-lookup"><span data-stu-id="4f4d6-122">Click to open the **Define Filters** dialog box.</span></span>  
  
 <span data-ttu-id="4f4d6-123">**Aplicar ou Remover Filtro**</span><span class="sxs-lookup"><span data-stu-id="4f4d6-123">**Apply or Remove Filter**</span></span>  
 <span data-ttu-id="4f4d6-124">Clique para aplicar ou remover um filtro definido na caixa de diálogo **Definir Filtros** .</span><span class="sxs-lookup"><span data-stu-id="4f4d6-124">Click to apply or remove a filter that has been defined in the **Define Filters** dialog box.</span></span>  
  
 <span data-ttu-id="4f4d6-125">**Selecionar tudo**</span><span class="sxs-lookup"><span data-stu-id="4f4d6-125">**Select All**</span></span>  
 <span data-ttu-id="4f4d6-126">Clique para selecionar todos os conflitos listados na grade.</span><span class="sxs-lookup"><span data-stu-id="4f4d6-126">Click to select all conflicts listed in the grid.</span></span>  
  
 <span data-ttu-id="4f4d6-127">**Selecionar nenhum**</span><span class="sxs-lookup"><span data-stu-id="4f4d6-127">**Select None**</span></span>  
 <span data-ttu-id="4f4d6-128">Clique para desmarcar a seleção de todos os conflitos listados na grade.</span><span class="sxs-lookup"><span data-stu-id="4f4d6-128">Click to deselect all conflicts listed in the grid.</span></span>  
  
 <span data-ttu-id="4f4d6-129">**Remover**</span><span class="sxs-lookup"><span data-stu-id="4f4d6-129">**Remove**</span></span>  
 <span data-ttu-id="4f4d6-130">Clique para remover conflitos selecionados do visualizador e seus metadados associados das tabelas do sistema de replicação.</span><span class="sxs-lookup"><span data-stu-id="4f4d6-130">Click to remove selected conflicts from the viewer and their associated metadata from the replication system tables.</span></span>  
  
 <span data-ttu-id="4f4d6-131">**Mostrar todas as colunas**</span><span class="sxs-lookup"><span data-stu-id="4f4d6-131">**Show all columns**</span></span>  
 <span data-ttu-id="4f4d6-132">Selecione para mostrar todas as colunas da tabela.</span><span class="sxs-lookup"><span data-stu-id="4f4d6-132">Select to show all columns of the table.</span></span>  
  
 <span data-ttu-id="4f4d6-133">**Mostrar as primeiras cinco colunas e outras colunas com dados conflitantes**</span><span class="sxs-lookup"><span data-stu-id="4f4d6-133">**Show first five columns and other columns with conflicting data**</span></span>  
 <span data-ttu-id="4f4d6-134">Selecione para exibir as primeiras cinco colunas e qualquer coluna com conflitos.</span><span class="sxs-lookup"><span data-stu-id="4f4d6-134">Select to display the first five columns and any columns that have conflicts.</span></span> <span data-ttu-id="4f4d6-135">Isso é útil quando a tabela tem um grande número de colunas, mas você quer ver apenas as mais relevantes para resolver o conflito.</span><span class="sxs-lookup"><span data-stu-id="4f4d6-135">This is helpful when the table has a large number of columns, but you want to see only the columns most relevant to resolving the conflict.</span></span> <span data-ttu-id="4f4d6-136">As primeiras cinco colunas sempre são incluídas nessa exibição, como campos que identificam uma linha, como chave primária ou campo de nomes, estão sempre entre as primeiras colunas da tabela.</span><span class="sxs-lookup"><span data-stu-id="4f4d6-136">The first five columns are always included in this view, as fields that identify a row, such as the primary key or name fields, are often among the first columns of the table.</span></span>  
  
 <span data-ttu-id="4f4d6-137">**Exibir Informações da Coluna** (**...**)</span><span class="sxs-lookup"><span data-stu-id="4f4d6-137">**Display Column Information** (**...**)</span></span>  
 <span data-ttu-id="4f4d6-138">Clique para exibir informações da coluna: **Nome da Tabela**, **Nome da Coluna**, **Tipo de Dados**e **Valor da Coluna**.</span><span class="sxs-lookup"><span data-stu-id="4f4d6-138">Click to view column information: **Table Name**, **Column Name**, **Data Type**, and **Column Value**.</span></span>  
  
 <span data-ttu-id="4f4d6-139">**Registrar em log os detalhes do conflito**</span><span class="sxs-lookup"><span data-stu-id="4f4d6-139">**Log the details of the conflict**</span></span>  
 <span data-ttu-id="4f4d6-140">Marque essa caixa para registrar em log os detalhes do conflito em um arquivo.</span><span class="sxs-lookup"><span data-stu-id="4f4d6-140">Check this box to log the details of the conflict to a file.</span></span> <span data-ttu-id="4f4d6-141">Para especificar um local para o arquivo, aponte para o menu **Exibir** e clique em **Opções**.</span><span class="sxs-lookup"><span data-stu-id="4f4d6-141">To specify a location for the file, point to the **View** menu and click **Options**.</span></span> <span data-ttu-id="4f4d6-142">Insira um valor ou clique em (**...**) e navegue até o arquivo apropriado.</span><span class="sxs-lookup"><span data-stu-id="4f4d6-142">Enter a value, or click the browse (**...**) and navigate to the appropriate file.</span></span> <span data-ttu-id="4f4d6-143">Clique em **OK** para sair da caixa de diálogo **Opções** .</span><span class="sxs-lookup"><span data-stu-id="4f4d6-143">Click **OK** to exit the **Options** dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f4d6-144">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="4f4d6-144">See Also</span></span>  
 <span data-ttu-id="4f4d6-145">[Detecção de conflitos na replicação ponto a ponto](transactional/peer-to-peer-conflict-detection-in-peer-to-peer-replication.md) </span><span class="sxs-lookup"><span data-stu-id="4f4d6-145">[Conflict Detection in Peer-to-Peer Replication](transactional/peer-to-peer-conflict-detection-in-peer-to-peer-replication.md) </span></span>  
 [<span data-ttu-id="4f4d6-146">Exibir conflitos de dados em publicações transacionais &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="4f4d6-146">View Data Conflicts for Transactional Publications &#40;SQL Server Management Studio&#41;</span></span>](view-data-conflicts-for-transactional-publications-sql-server-management-studio.md)  
  
  
