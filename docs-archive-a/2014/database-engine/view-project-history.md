---
title: Exibir histórico do projeto | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- viewing project history
- version control services [SQL Server], project history
- projects [SQL Server Management Studio], historical information
- historical information [SQL Server], projects
ms.assetid: be0ea2ac-4a35-429c-9c9e-4001ea9035a4
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 85028141050e19e6ed6394a5bb17709ac8f906ee
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583180"
---
# <a name="view-project-history"></a><span data-ttu-id="0f768-102">Exibir histórico de projetos</span><span class="sxs-lookup"><span data-stu-id="0f768-102">View Project History</span></span>
  <span data-ttu-id="0f768-103">O histórico de um projeto do [!INCLUDE[msCoName](../includes/msconame-md.md)] Visual SourceSafe (VSS) inclui uma lista de todas as ações executadas em cada um dos arquivos do projeto, incluindo criação, adição, exclusão e recuperação de arquivos.</span><span class="sxs-lookup"><span data-stu-id="0f768-103">The history of a [!INCLUDE[msCoName](../includes/msconame-md.md)] Visual SourceSafe (VSS) project includes a list of all the actions taken on each of the project files, including file creation, addition, deletion, and recovery.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0f768-104">Um projeto do Visual SourceSafe normalmente é chamado de pasta do servidor de controle do código-fonte, o local em que a versão do servidor de um arquivo com controle do código-fonte é armazenado no servidor.</span><span class="sxs-lookup"><span data-stu-id="0f768-104">A Visual SourceSafe project is more commonly referred to as the source control server folder, the location where the server version of a source-controlled file is stored on the server.</span></span>  
  
 <span data-ttu-id="0f768-105">Você pode usar o [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] para examinar o histórico do projeto do Visual SourceSafe a que a solução atual pertence.</span><span class="sxs-lookup"><span data-stu-id="0f768-105">You can use [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] to examine the history of the Visual SourceSafe project to which the currently loaded solution belongs.</span></span> <span data-ttu-id="0f768-106">Com base nas informações exibidas como parte do histórico de um projeto, você pode recuperar cópias locais das versões de arquivo, restaurar versões excluídas ou compartilhar uma versão de arquivo entre projetos.</span><span class="sxs-lookup"><span data-stu-id="0f768-106">Based on the information displayed as part of the history of a project, you can retrieve local copies of file versions, restore deleted versions, or share a file version between projects.</span></span>  
  
### <a name="to-view-the-history-of-a-vss-project"></a><span data-ttu-id="0f768-107">Para exibir o histórico de um projeto do VSS</span><span class="sxs-lookup"><span data-stu-id="0f768-107">To view the history of a VSS project</span></span>  
  
1.  <span data-ttu-id="0f768-108">No Gerenciador de Soluções, selecione o projeto.</span><span class="sxs-lookup"><span data-stu-id="0f768-108">In Solution Explorer, select the project.</span></span>  
  
2.  <span data-ttu-id="0f768-109">No menu **arquivo** , aponte para **controle do código-fonte** e clique em **Exibir histórico**.</span><span class="sxs-lookup"><span data-stu-id="0f768-109">On the **File** menu, point to **Source Control** and click **View History**.</span></span>  
  
3.  <span data-ttu-id="0f768-110">Na caixa **de diálogo histórico de** \<Project> , execute qualquer uma das seguintes ações:</span><span class="sxs-lookup"><span data-stu-id="0f768-110">In the **History of** \<Project> dialog box, perform any of the following actions:</span></span>  
  
    -   <span data-ttu-id="0f768-111">Exiba a cópia do sistema de controle do código-fonte de um arquivo selecionado.</span><span class="sxs-lookup"><span data-stu-id="0f768-111">View the source control system's copy of a selected file.</span></span>  
  
    -   <span data-ttu-id="0f768-112">Exiba as informações detalhadas de um arquivo selecionado.</span><span class="sxs-lookup"><span data-stu-id="0f768-112">View detailed information about a selected file.</span></span>  
  
    -   <span data-ttu-id="0f768-113">Recupere um arquivo selecionado para o disco local.</span><span class="sxs-lookup"><span data-stu-id="0f768-113">Retrieve a selected file to your local disk.</span></span>  
  
    -   <span data-ttu-id="0f768-114">Faça o check-out de um arquivo selecionado.</span><span class="sxs-lookup"><span data-stu-id="0f768-114">Check out a selected file.</span></span>  
  
    -   <span data-ttu-id="0f768-115">Compartilhe um arquivo selecionado entre dois projetos de controle do código-fonte.</span><span class="sxs-lookup"><span data-stu-id="0f768-115">Share a selected file between two source control projects.</span></span>  
  
    -   <span data-ttu-id="0f768-116">Exporte o relatório de histórico para uma impressora, um arquivo ou para a área de transferência.</span><span class="sxs-lookup"><span data-stu-id="0f768-116">Export the history report to a printer, a file, or the Clipboard.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0f768-117">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="0f768-117">See Also</span></span>  
 <span data-ttu-id="0f768-118">[Definir e recuperar informações de versão](../../2014/database-engine/set-and-retrieve-version-information.md) </span><span class="sxs-lookup"><span data-stu-id="0f768-118">[Set and Retrieve Version Information](../../2014/database-engine/set-and-retrieve-version-information.md) </span></span>  
 <span data-ttu-id="0f768-119">[Exibir status do arquivo](../../2014/database-engine/view-file-status.md) </span><span class="sxs-lookup"><span data-stu-id="0f768-119">[View File Status](../../2014/database-engine/view-file-status.md) </span></span>  
 <span data-ttu-id="0f768-120">[Recuperar arquivos](../../2014/database-engine/retrieve-files.md) </span><span class="sxs-lookup"><span data-stu-id="0f768-120">[Retrieve Files](../../2014/database-engine/retrieve-files.md) </span></span>  
 [<span data-ttu-id="0f768-121">Comparar arquivos</span><span class="sxs-lookup"><span data-stu-id="0f768-121">Compare Files</span></span>](../../2014/database-engine/compare-files.md)  
  
  
