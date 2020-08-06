---
title: Remover colunas de uma estrutura de mineração | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- mining structures [Analysis Services], columns
- removing columns
- deleting columns
- columns [data mining], mining structure columns
ms.assetid: 41073ffe-9351-416b-9f0c-62634bc213f9
author: minewiskan
ms.author: owend
ms.openlocfilehash: 44ad1de08d57d00fd9798e1ceeddb85d146d7111
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87568896"
---
# <a name="remove-columns-from-a-mining-structure"></a><span data-ttu-id="4a64c-102">Remover colunas de uma estrutura de mineração</span><span class="sxs-lookup"><span data-stu-id="4a64c-102">Remove Columns from a Mining Structure</span></span>
  <span data-ttu-id="4a64c-103">Você pode usar o Designer de Mineração de Dados para remover colunas de uma estrutura de mineração após a criação da estrutura.</span><span class="sxs-lookup"><span data-stu-id="4a64c-103">You can use Data Mining Designer to remove columns from a mining structure after the structure has already been created.</span></span> <span data-ttu-id="4a64c-104">Alguns motivos para remover uma coluna da estrutura de mineração:</span><span class="sxs-lookup"><span data-stu-id="4a64c-104">Reasons to remove a mining structure column might include the following:</span></span>  
  
-   <span data-ttu-id="4a64c-105">A estrutura de mineração contém várias cópias de uma coluna e você deseja evitar o uso de dados duplicados em um modelo.</span><span class="sxs-lookup"><span data-stu-id="4a64c-105">The mining structure contains multiple copies of a column and you want to avoid the use of duplicate data in a model.</span></span>  
  
-   <span data-ttu-id="4a64c-106">Os dados devem ser protegidos, mas o detalhamento foi habilitado.</span><span class="sxs-lookup"><span data-stu-id="4a64c-106">The data should be protected, but drillthrough has been enabled.</span></span>  
  
-   <span data-ttu-id="4a64c-107">Os dados não são usados na modelagem e não devem ser processados.</span><span class="sxs-lookup"><span data-stu-id="4a64c-107">The data is unused in modeling and should not be processed.</span></span>  
  
 <span data-ttu-id="4a64c-108">A exclusão de uma coluna da estrutura de mineração não altera a coluna na exibição da fonte de dados nem nos dados externos; apenas os metadados são excluídos.</span><span class="sxs-lookup"><span data-stu-id="4a64c-108">Deleting a column from the mining structure does not change the column in the data source view or in the external data; only metadata is deleted.</span></span> <span data-ttu-id="4a64c-109">Entretanto, quando você altera as colunas usadas em uma estrutura de mineração, precisa reprocessar a estrutura e quaisquer modelos com base nela.</span><span class="sxs-lookup"><span data-stu-id="4a64c-109">However, when you change the columns used in a mining structure, you must reprocess the structure and any models based on it.</span></span>  
  
### <a name="to-remove-a-column-from-the-mining-structure"></a><span data-ttu-id="4a64c-110">Para remover colunas de uma estrutura de mineração</span><span class="sxs-lookup"><span data-stu-id="4a64c-110">To remove a column from the mining structure</span></span>  
  
1.  <span data-ttu-id="4a64c-111">Selecione a guia **Estrutura de Mineração** no Designer de Mineração de Dados.</span><span class="sxs-lookup"><span data-stu-id="4a64c-111">Select the **Mining Structure** tab in Data Mining Designer.</span></span>  
  
2.  <span data-ttu-id="4a64c-112">Expanda a árvore da estrutura de mineração para que mostre todas as colunas.</span><span class="sxs-lookup"><span data-stu-id="4a64c-112">Expand the tree for the mining structure, to show all the columns.</span></span>  
  
3.  <span data-ttu-id="4a64c-113">Clique com o botão direito do mouse na coluna que você quer excluir e selecione **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="4a64c-113">Right-click the column that you want to delete, and then select **Delete**.</span></span>  
  
4.  <span data-ttu-id="4a64c-114">Na caixa de diálogo **Excluir Objetos** , clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="4a64c-114">In the **Delete Objects** dialog box, click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a64c-115">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="4a64c-115">See Also</span></span>  
 [<span data-ttu-id="4a64c-116">Tarefas e instruções da estrutura de mineração</span><span class="sxs-lookup"><span data-stu-id="4a64c-116">Mining Structure Tasks and How-tos</span></span>](mining-structure-tasks-and-how-tos.md)  
  
  
