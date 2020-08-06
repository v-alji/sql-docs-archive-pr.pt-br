---
title: Excluir arquivos do controle do código-fonte | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- excluding files from source control
- source controls [SQL Server Management Studio], file exclusions
ms.assetid: 7dcb6514-db5c-49eb-8b5a-2c766ce39aa7
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 9fb3c5ccb4fcaad062236eec6d04f995557dc2b8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681086"
---
# <a name="exclude-files-from-source-control"></a><span data-ttu-id="ca868-102">Excluir arquivos do controle do código-fonte</span><span class="sxs-lookup"><span data-stu-id="ca868-102">Exclude Files from Source Control</span></span>
  <span data-ttu-id="ca868-103">Se a solução na qual você está trabalhando contiver arquivos que não exigem serviços de controle do código-fonte, você poderá usar o comando **excluir do controle do código-fonte** para excluir o arquivo do controle do código-fonte.</span><span class="sxs-lookup"><span data-stu-id="ca868-103">If the solution you are working on contains files that do not require source control services, you can use the **Exclude from Source Control** command to exclude the file from source control.</span></span> <span data-ttu-id="ca868-104">Quando você faz isso, o arquivo permanece no banco de dados do [!INCLUDE[msCoName](../includes/msconame-md.md)] Visual SourceSafe, mas já não é feito o check-in ou check-out com o projeto.</span><span class="sxs-lookup"><span data-stu-id="ca868-104">When you do this, the file remains in the [!INCLUDE[msCoName](../includes/msconame-md.md)] Visual SourceSafe database, but it is no longer checked in or out with the project.</span></span>  
  
 <span data-ttu-id="ca868-105">Você deve usar o comando **excluir do controle do código-fonte** somente em arquivos gerados.</span><span class="sxs-lookup"><span data-stu-id="ca868-105">You should use the **Exclude from Source Control** command only on generated files.</span></span> <span data-ttu-id="ca868-106">Um arquivo gerado é aquele que pode ser totalmente recriado [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] com base no conteúdo de outro arquivo na solução.</span><span class="sxs-lookup"><span data-stu-id="ca868-106">A generated file is one that can be entirely re-created by [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] based on the contents of another file in the solution.</span></span>  
  
### <a name="to-exclude-a-file-from-source-control"></a><span data-ttu-id="ca868-107">Para excluir arquivos do controle de código-fonte</span><span class="sxs-lookup"><span data-stu-id="ca868-107">To exclude a file from source control</span></span>  
  
1.  <span data-ttu-id="ca868-108">No Gerenciador de Soluções, selecione o arquivo que irá excluir.</span><span class="sxs-lookup"><span data-stu-id="ca868-108">In Solution Explorer, select the file to exclude.</span></span>  
  
2.  <span data-ttu-id="ca868-109">No menu **arquivo** , aponte para **controle do código-fonte**e clique em **excluir** *\<file name>* **do controle do código-fonte**.</span><span class="sxs-lookup"><span data-stu-id="ca868-109">On the **File** menu, point to **Source Control**, and then click **Exclude** *\<file name>* **from Source Control**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca868-110">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="ca868-110">See Also</span></span>  
 <span data-ttu-id="ca868-111">[Noções básicas do controle do código-fonte](../../2014/database-engine/source-control-basics.md) </span><span class="sxs-lookup"><span data-stu-id="ca868-111">[Source Control Basics](../../2014/database-engine/source-control-basics.md) </span></span>  
 <span data-ttu-id="ca868-112">[Definir opções de controle do código-fonte](../../2014/database-engine/set-source-control-options.md) </span><span class="sxs-lookup"><span data-stu-id="ca868-112">[Set Source Control Options](../../2014/database-engine/set-source-control-options.md) </span></span>  
 [<span data-ttu-id="ca868-113">Alterar conexões de controle do código-fonte</span><span class="sxs-lookup"><span data-stu-id="ca868-113">Change Source Control Connections</span></span>](../../2014/database-engine/change-source-control-connections.md)  
  
  
