---
title: Definir e recuperar informações de versão | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- historical information [SQL Server]
- source controls [SQL Server Management Studio], version information
- retrieving version information
- current file version information
- version control services [SQL Server], retrieving version information
- version control services [SQL Server], setting version information
- status information [SQL Server], source control files
- historical information [SQL Server], source control files
ms.assetid: c3f253c4-4e3d-48e8-8d90-bd6ee899faf7
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: eff3d40ba9b663ba8611508c5b9f0c9961005b81
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678949"
---
# <a name="set-and-retrieve-version-information"></a><span data-ttu-id="96354-102">Definir e recuperar informações de versão</span><span class="sxs-lookup"><span data-stu-id="96354-102">Set and Retrieve Version Information</span></span>
  <span data-ttu-id="96354-103">As informações de versão incluem o histórico e o status atual de um arquivo com controle do código-fonte.</span><span class="sxs-lookup"><span data-stu-id="96354-103">Version information includes the history and current status of a source-controlled file.</span></span> <span data-ttu-id="96354-104">Para todo arquivo com controle do código-fonte, o [!INCLUDE[msCoName](../includes/msconame-md.md)] Visual SourceSafe mantém um histórico abrangente, de forma que você pode localizar a evolução de um ou mais arquivos com o passar do tempo.</span><span class="sxs-lookup"><span data-stu-id="96354-104">For every source-controlled file, [!INCLUDE[msCoName](../includes/msconame-md.md)] Visual SourceSafe maintains a comprehensive history, so you can track the evolution of one or more files over time.</span></span> <span data-ttu-id="96354-105">Você também pode usar essas informações para recuperar uma cópia local de qualquer versão do arquivo ou comparar duas versões de arquivos.</span><span class="sxs-lookup"><span data-stu-id="96354-105">You can also use this information to retrieve a local copy of any version of the file or to compare any two file versions.</span></span>  
  
 <span data-ttu-id="96354-106">O histórico de um arquivo inclui:</span><span class="sxs-lookup"><span data-stu-id="96354-106">The history of a file includes:</span></span>  
  
-   <span data-ttu-id="96354-107">O número de versão que identifica sua sequência entre outras versões do mesmo arquivo.</span><span class="sxs-lookup"><span data-stu-id="96354-107">The version number, which identifies its sequence among other versions of the same file.</span></span>  
  
-   <span data-ttu-id="96354-108">A ação executada.</span><span class="sxs-lookup"><span data-stu-id="96354-108">The action performed.</span></span> <span data-ttu-id="96354-109">Operações rastreadas incluem criação de arquivo, check-in e exclusão.</span><span class="sxs-lookup"><span data-stu-id="96354-109">Tracked operations include file creation, check in, and deletion.</span></span>  
  
-   <span data-ttu-id="96354-110">O nome do usuário que executou uma ação envolvendo o arquivo.</span><span class="sxs-lookup"><span data-stu-id="96354-110">The user name of the person who performed an action involving the file.</span></span>  
  
-   <span data-ttu-id="96354-111">A data e hora em que a operação foi executada.</span><span class="sxs-lookup"><span data-stu-id="96354-111">The date and time when the operation was performed.</span></span>  
  
 <span data-ttu-id="96354-112">O Visual SourceSafe também mantém informações sobre o status atual da solução carregada.</span><span class="sxs-lookup"><span data-stu-id="96354-112">Visual SourceSafe also maintains current status information on the currently loaded solution.</span></span> <span data-ttu-id="96354-113">Essas informações fornecem um instantâneo do status atual do arquivo, incluindo:</span><span class="sxs-lookup"><span data-stu-id="96354-113">This information provides a snapshot of the current state of the file, including:</span></span>  
  
-   <span data-ttu-id="96354-114">A identidade do usuário que fez o check-out do arquivo.</span><span class="sxs-lookup"><span data-stu-id="96354-114">The identity of the user who has the file checked out.</span></span>  
  
-   <span data-ttu-id="96354-115">A versão mais recente do arquivo selecionado.</span><span class="sxs-lookup"><span data-stu-id="96354-115">The latest version number of the selected file.</span></span>  
  
-   <span data-ttu-id="96354-116">A data em que a versão foi criada.</span><span class="sxs-lookup"><span data-stu-id="96354-116">The date when the version was created.</span></span>  
  
-   <span data-ttu-id="96354-117">O comentário do usuário associado com a versão.</span><span class="sxs-lookup"><span data-stu-id="96354-117">The user comment associated with the version.</span></span>  
  
-   <span data-ttu-id="96354-118">Os caminhos dos projetos com os quais o arquivo é compartilhado.</span><span class="sxs-lookup"><span data-stu-id="96354-118">The paths to the projects with which the file is shared.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="96354-119">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="96354-119">In This Section</span></span>  
  
-   [<span data-ttu-id="96354-120">Exibir o histórico de arquivos</span><span class="sxs-lookup"><span data-stu-id="96354-120">View File History</span></span>](../../2014/database-engine/view-file-history.md)  
  
-   [<span data-ttu-id="96354-121">Exibir histórico de projetos</span><span class="sxs-lookup"><span data-stu-id="96354-121">View Project History</span></span>](../../2014/database-engine/view-project-history.md)  
  
-   [<span data-ttu-id="96354-122">Exibir status de arquivos</span><span class="sxs-lookup"><span data-stu-id="96354-122">View File Status</span></span>](../../2014/database-engine/view-file-status.md)  
  
-   [<span data-ttu-id="96354-123">Recuperar arquivos</span><span class="sxs-lookup"><span data-stu-id="96354-123">Retrieve Files</span></span>](../../2014/database-engine/retrieve-files.md)  
  
-   [<span data-ttu-id="96354-124">Especificar uma versão como a versão mais recente</span><span class="sxs-lookup"><span data-stu-id="96354-124">Specify a Version as the Latest Version</span></span>](../../2014/database-engine/specify-a-version-as-the-latest-version.md)  
  
-   [<span data-ttu-id="96354-125">Comparar arquivos</span><span class="sxs-lookup"><span data-stu-id="96354-125">Compare Files</span></span>](../../2014/database-engine/compare-files.md)  
  
-   [<span data-ttu-id="96354-126">Compartilhar arquivos</span><span class="sxs-lookup"><span data-stu-id="96354-126">Share Files</span></span>](../../2014/database-engine/share-files.md)  
  
-   [<span data-ttu-id="96354-127">Criar histórico e relatórios de status</span><span class="sxs-lookup"><span data-stu-id="96354-127">Create History and Status Reports</span></span>](../../2014/database-engine/create-history-and-status-reports.md)  
  
## <a name="see-also"></a><span data-ttu-id="96354-128">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="96354-128">See Also</span></span>  
 [<span data-ttu-id="96354-129">Noções básicas de controle do código-fonte</span><span class="sxs-lookup"><span data-stu-id="96354-129">Source Control Basics</span></span>](../../2014/database-engine/source-control-basics.md)  
  
  
