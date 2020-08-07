---
title: Comparar arquivos | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- versions [SQL Server], file comparisons
- comparing files
- file comparisons [SQL Server]
ms.assetid: 728811c4-5d7a-4420-abce-f56c5a0994d2
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: f29bf7098f0c73d0b672e20b973b1347349b31f2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575361"
---
# <a name="compare-files"></a><span data-ttu-id="767d0-102">Comparar arquivos</span><span class="sxs-lookup"><span data-stu-id="767d0-102">Compare Files</span></span>
  <span data-ttu-id="767d0-103">Você pode comparar arquivos para determinar como um arquivo progrediu até chegar a seu estado atual.</span><span class="sxs-lookup"><span data-stu-id="767d0-103">You can compare files to determine how a file has progressed to its present state.</span></span> <span data-ttu-id="767d0-104">Por exemplo, se você detectar um defeito em uma compilação do projeto de código depois de fazer check-in de uma versão de arquivo de origem em particular, poderá comparar a versão atual do arquivo com uma versão anterior.</span><span class="sxs-lookup"><span data-stu-id="767d0-104">For example, if you detect a defect in a build of your code project after a particular source file version is checked in, you can compare the current file version to a previous one.</span></span> <span data-ttu-id="767d0-105">Isso o ajuda a definir o código que introduziu o problema.</span><span class="sxs-lookup"><span data-stu-id="767d0-105">This helps you to pinpoint the code that introduced the defect.</span></span>  
  
 <span data-ttu-id="767d0-106">Você pode usar o [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] para comparar uma cópia local de um projeto com a versão armazenada no controle do código-fonte ou comparar dois arquivos locais.</span><span class="sxs-lookup"><span data-stu-id="767d0-106">You can use [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] to compare a local copy of a project or file to the version stored in source control, or to compare two local files.</span></span> <span data-ttu-id="767d0-107">Além disso, usando o comando **history** , você pode comparar quaisquer duas versões controladas por fonte.</span><span class="sxs-lookup"><span data-stu-id="767d0-107">Also, using the **History** command, you can compare any two source-controlled versions.</span></span>  
  
### <a name="to-compare-files"></a><span data-ttu-id="767d0-108">Para comparar arquivos</span><span class="sxs-lookup"><span data-stu-id="767d0-108">To compare files</span></span>  
  
1.  <span data-ttu-id="767d0-109">No Gerenciador de Soluções, selecione um projeto ou um dos arquivos do projeto.</span><span class="sxs-lookup"><span data-stu-id="767d0-109">In Solution Explorer, select either a project or one of the project files.</span></span>  
  
2.  <span data-ttu-id="767d0-110">No menu **arquivo** , aponte para **controle do código-fonte**e clique em **comparar**.</span><span class="sxs-lookup"><span data-stu-id="767d0-110">On the **File** menu, point to **Source Control**, and click **Compare**.</span></span>  
  
3.  <span data-ttu-id="767d0-111">Na caixa de diálogo **Opções de diferença** , selecione as opções apropriadas e, em seguida, clique em **relatório**.</span><span class="sxs-lookup"><span data-stu-id="767d0-111">In the **Difference Options** dialog box, select the appropriate options, and then click **Report**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="767d0-112">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="767d0-112">See Also</span></span>  
 <span data-ttu-id="767d0-113">[Definir e recuperar informações de versão](../../2014/database-engine/set-and-retrieve-version-information.md) </span><span class="sxs-lookup"><span data-stu-id="767d0-113">[Set and Retrieve Version Information](../../2014/database-engine/set-and-retrieve-version-information.md) </span></span>  
 <span data-ttu-id="767d0-114">[Exibir histórico de arquivo](../../2014/database-engine/view-file-history.md) </span><span class="sxs-lookup"><span data-stu-id="767d0-114">[View File History](../../2014/database-engine/view-file-history.md) </span></span>  
 <span data-ttu-id="767d0-115">[Exibir histórico do projeto](../../2014/database-engine/view-project-history.md) </span><span class="sxs-lookup"><span data-stu-id="767d0-115">[View Project History](../../2014/database-engine/view-project-history.md) </span></span>  
 <span data-ttu-id="767d0-116">[Exibir status do arquivo](../../2014/database-engine/view-file-status.md) </span><span class="sxs-lookup"><span data-stu-id="767d0-116">[View File Status](../../2014/database-engine/view-file-status.md) </span></span>  
 [<span data-ttu-id="767d0-117">Recuperar arquivos</span><span class="sxs-lookup"><span data-stu-id="767d0-117">Retrieve Files</span></span>](../../2014/database-engine/retrieve-files.md)  
  
  
