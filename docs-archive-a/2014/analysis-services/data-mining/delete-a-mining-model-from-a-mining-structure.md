---
title: Excluir um modelo de mineração de uma estrutura de mineração | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- mining structures [Analysis Services], mining models
- deleting mining models
- removing mining models
- mining models [Analysis Services], deleting
ms.assetid: 9ab1506b-856e-4762-a663-5adf15ac71e3
author: minewiskan
ms.author: owend
ms.openlocfilehash: 72c79dcdccf6225b8e75144f8b090dcab7506c10
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582215"
---
# <a name="delete-a-mining-model-from-a-mining-structure"></a><span data-ttu-id="e7f8a-102">Excluir um modelo de mineração de uma estrutura de mineração</span><span class="sxs-lookup"><span data-stu-id="e7f8a-102">Delete a Mining Model from a Mining Structure</span></span>
  <span data-ttu-id="e7f8a-103">Você pode excluir modelos de mineração usando o Designer de Mineração de Dados, o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]ou instruções DMX.</span><span class="sxs-lookup"><span data-stu-id="e7f8a-103">You can delete mining models by using Data Mining Designer, by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], or by using DMX statements.</span></span>  
  
### <a name="delete-a-mining-model-using-sql-server-data-tools"></a><span data-ttu-id="e7f8a-104">Exclua um modelo de mineração usando as Ferramentas de Dados do SQL Server</span><span class="sxs-lookup"><span data-stu-id="e7f8a-104">Delete a mining model using SQL Server Data Tools</span></span>  
  
1.  <span data-ttu-id="e7f8a-105">Selecione a guia **Modelos de Mineração** no [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e7f8a-105">Select the **Mining Models** tab in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span></span>  
  
2.  <span data-ttu-id="e7f8a-106">Clique com o botão direito do mouse no modelo a ser excluído e selecione **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="e7f8a-106">Right-click the model that you want to delete, and select **Delete**.</span></span>  
  
     <span data-ttu-id="e7f8a-107">A caixa de diálogo **Excluir Objetos** é aberta.</span><span class="sxs-lookup"><span data-stu-id="e7f8a-107">The **Delete Objects** dialog box opens.</span></span>  
  
3.  <span data-ttu-id="e7f8a-108">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="e7f8a-108">Click **OK**.</span></span>  
  
### <a name="delete-a-mining-model-using-sql-server-management-studio"></a><span data-ttu-id="e7f8a-109">Exclua um modelo de mineração usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="e7f8a-109">Delete a mining model using SQL Server Management Studio</span></span>  
  
1.  <span data-ttu-id="e7f8a-110">No [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], abra o banco de dados [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] que contém o modelo.</span><span class="sxs-lookup"><span data-stu-id="e7f8a-110">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], open the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database that contains the model.</span></span>  
  
2.  <span data-ttu-id="e7f8a-111">Expanda **Estruturas de Mineração**e, depois, **Modelos de Mineração**.</span><span class="sxs-lookup"><span data-stu-id="e7f8a-111">Expand **Mining Structures**, and then expand **Mining Models**.</span></span>  
  
3.  <span data-ttu-id="e7f8a-112">Clique com o botão direito do mouse no modelo a ser excluído e selecione **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="e7f8a-112">Right-click the model you want to delete, and select **Delete**.</span></span>  
  
     <span data-ttu-id="e7f8a-113">A exclusão do modelo não leva à exclusão dos dados de treinamento, mas apenas dos metadados e de quaisquer padrões criados durante o treinamento do modelo.</span><span class="sxs-lookup"><span data-stu-id="e7f8a-113">Deleting the model does not delete the training data, only the metadata and any patterns created when you trained the model.</span></span>  
  
### <a name="delete-a-mining-model-using-dmx"></a><span data-ttu-id="e7f8a-114">Excluir um modelo de mineração usando DMX</span><span class="sxs-lookup"><span data-stu-id="e7f8a-114">Delete a mining model using DMX</span></span>  
  
-   [<span data-ttu-id="e7f8a-115">DROP MINING MODEL &#40;DMX&#41;</span><span class="sxs-lookup"><span data-stu-id="e7f8a-115">DROP MINING MODEL &#40;DMX&#41;</span></span>](/sql/dmx/drop-mining-model-dmx)  
  
## <a name="see-also"></a><span data-ttu-id="e7f8a-116">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="e7f8a-116">See Also</span></span>  
 [<span data-ttu-id="e7f8a-117">Tarefas e instruções do modelo de mineração</span><span class="sxs-lookup"><span data-stu-id="e7f8a-117">Mining Model Tasks and How-tos</span></span>](mining-model-tasks-and-how-tos.md)  
  
  
