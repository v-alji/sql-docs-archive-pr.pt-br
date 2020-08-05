---
title: Propriedades do banco de dados (página Grupos de Arquivos) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
f1_keywords:
- sql12.swb.databaseproperties.filegroups.f1
ms.assetid: 8d06e859-73dd-4019-b6e8-99c5c5297697
author: stevestein
ms.author: sstein
ms.openlocfilehash: d0546a17491ed5d3b36890a605c5faa922c24fe6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573104"
---
# <a name="database-properties-filegroups-page"></a><span data-ttu-id="c3e74-102">Propriedades do banco de dados (página Grupos de Arquivos)</span><span class="sxs-lookup"><span data-stu-id="c3e74-102">Database Properties (Filegroups Page)</span></span>
  <span data-ttu-id="c3e74-103">Use esta página para exibir os grupos de arquivos ou para adicionar um grupo de arquivos novo ao banco de dados selecionado.</span><span class="sxs-lookup"><span data-stu-id="c3e74-103">Use this page to view the filegroups or add a new filegroup to the selected database.</span></span> <span data-ttu-id="c3e74-104">Os tipos de grupos de arquivos estão separados em grupos de arquivos *row* , dados FILESTREAM e grupos de arquivos com otimização de memória.</span><span class="sxs-lookup"><span data-stu-id="c3e74-104">Filegroup types are separated into *row* filegroups, FILESTREAM data, and memory-optimized filegroups.</span></span>  
  
 <span data-ttu-id="c3e74-105">Os grupos de arquivos tipo linha contêm dados e arquivos de log normais.</span><span class="sxs-lookup"><span data-stu-id="c3e74-105">Row filegroups contain regular data and log files.</span></span> <span data-ttu-id="c3e74-106">Os grupos de arquivos de dados FILESTREAM contêm arquivos de dados FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="c3e74-106">FILESTREAM data filegroups contain FILESTREAM data files.</span></span> <span data-ttu-id="c3e74-107">Esses arquivos de dados armazenam informações sobre como os dados de objetos binários grandes (BLOB) são salvos no sistema de arquivos quando usar o armazenamento FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="c3e74-107">These data files store information about how binary large object (BLOB) data is stored on the file system when you are using FILESTREAM storage.</span></span> <span data-ttu-id="c3e74-108">As opções são as mesmas para os dois tipos de grupos de arquivos.</span><span class="sxs-lookup"><span data-stu-id="c3e74-108">The options are the same for both types of filegroups.</span></span>  
  
 <span data-ttu-id="c3e74-109">Se o FILESTREAM não estiver habilitado, a seção **Fluxo de arquivos** não estará disponível.</span><span class="sxs-lookup"><span data-stu-id="c3e74-109">If FILESTREAM is not enabled, the **Filestream** section will not be available.</span></span> <span data-ttu-id="c3e74-110">Você pode habilitar o armazenamento FILESTREAM usando as [Propriedades do Servidor (Página Avançada)](../../database-engine/configure-windows/server-properties-advanced-page.md).</span><span class="sxs-lookup"><span data-stu-id="c3e74-110">You can enable FILESTREAM storage by using [Server Properties (Advanced Page)](../../database-engine/configure-windows/server-properties-advanced-page.md).</span></span>  
  
 <span data-ttu-id="c3e74-111">Para obter informações sobre como o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] usa grupos de arquivos linha, veja [Arquivos e grupos de arquivos do banco de dados](database-files-and-filegroups.md).</span><span class="sxs-lookup"><span data-stu-id="c3e74-111">For information about how [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] uses row filegroups, see [Database Files and Filegroups](database-files-and-filegroups.md).</span></span> <span data-ttu-id="c3e74-112">Para obter mais informações sobre os dados de FILESTREAM e os grupos de arquivos, veja [FILESTREAM &#40;SQL Server&#41;](../blob/filestream-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="c3e74-112">For more information about FILESTREAM data and filegroups, see [FILESTREAM &#40;SQL Server&#41;](../blob/filestream-sql-server.md).</span></span>  
  
 <span data-ttu-id="c3e74-113">Os grupos de arquivos com otimização de memória são necessários para um banco de dados conter uma ou mais tabelas com otimização de memória.</span><span class="sxs-lookup"><span data-stu-id="c3e74-113">Memory-optimized file groups are required for a database to contain one or more memory-optimized tables.</span></span>  
  
## <a name="row-and-filestream-data-filegroup-options"></a><span data-ttu-id="c3e74-114">Opções de grupo de arquivos de dados de linha e FILESTREAM</span><span class="sxs-lookup"><span data-stu-id="c3e74-114">Row and FILESTREAM Data Filegroup Options</span></span>  
 <span data-ttu-id="c3e74-115">**Nome**</span><span class="sxs-lookup"><span data-stu-id="c3e74-115">**Name**</span></span>  
 <span data-ttu-id="c3e74-116">Digite o nome do grupo de arquivos.</span><span class="sxs-lookup"><span data-stu-id="c3e74-116">Enter the name of the filegroup.</span></span>  
  
 <span data-ttu-id="c3e74-117">**Arquivos**</span><span class="sxs-lookup"><span data-stu-id="c3e74-117">**Files**</span></span>  
 <span data-ttu-id="c3e74-118">Exibe a contagem dos arquivos no grupo de arquivos.</span><span class="sxs-lookup"><span data-stu-id="c3e74-118">Displays the count of files in the filegroup.</span></span>  
  
 <span data-ttu-id="c3e74-119">**Somente leitura**</span><span class="sxs-lookup"><span data-stu-id="c3e74-119">**Read-only**</span></span>  
 <span data-ttu-id="c3e74-120">Selecione para definir o grupo de arquivos com o status de somente leitura.</span><span class="sxs-lookup"><span data-stu-id="c3e74-120">Select to set the filegroup to a read-only status.</span></span>  
  
 <span data-ttu-id="c3e74-121">**Default**</span><span class="sxs-lookup"><span data-stu-id="c3e74-121">**Default**</span></span>  
 <span data-ttu-id="c3e74-122">Selecione para tornar este grupo de arquivos o grupo de arquivos padrão.</span><span class="sxs-lookup"><span data-stu-id="c3e74-122">Select to make this filegroup the default filegroup.</span></span> <span data-ttu-id="c3e74-123">Você pode ter um grupo de arquivos padrão para linha e outro para os dados do FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="c3e74-123">You can have one default filegroup for rows and one default filegroup for FILESTREAM data.</span></span>  
  
 <span data-ttu-id="c3e74-124">**Adicionar**</span><span class="sxs-lookup"><span data-stu-id="c3e74-124">**Add**</span></span>  
 <span data-ttu-id="c3e74-125">Adiciona uma nova linha em branco aos grupos de arquivos da listagem de grade do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="c3e74-125">Adds a new blank row to the grid listing filegroups for the database.</span></span>  
  
 <span data-ttu-id="c3e74-126">**Remover**</span><span class="sxs-lookup"><span data-stu-id="c3e74-126">**Remove**</span></span>  
 <span data-ttu-id="c3e74-127">Remove da grade a linha do grupo de arquivos selecionada.</span><span class="sxs-lookup"><span data-stu-id="c3e74-127">Removes the selected filegroup row from the grid.</span></span>  
  
## <a name="memory-optimized-data-filegroup-options"></a><span data-ttu-id="c3e74-128">Opções de grupo de arquivos de dados com otimização de memória</span><span class="sxs-lookup"><span data-stu-id="c3e74-128">Memory-Optimized Data Filegroup Options</span></span>  
 <span data-ttu-id="c3e74-129">**Nome**</span><span class="sxs-lookup"><span data-stu-id="c3e74-129">**Name**</span></span>  
 <span data-ttu-id="c3e74-130">Digite o nome do grupo de arquivos com otimização de memória.</span><span class="sxs-lookup"><span data-stu-id="c3e74-130">Enter the name of the memory-optimized filegroup.</span></span>  
  
 <span data-ttu-id="c3e74-131">**Arquivos Filestream**</span><span class="sxs-lookup"><span data-stu-id="c3e74-131">**Filestream Files**</span></span>  
 <span data-ttu-id="c3e74-132">Exibe o número de arquivos (contêineres) no grupo de arquivos de dados com otimização de memória.</span><span class="sxs-lookup"><span data-stu-id="c3e74-132">Displays the number of files (containers) in the memory-optimized data filegroup.</span></span> <span data-ttu-id="c3e74-133">Você pode adicionar contêineres na página **Arquivos** .</span><span class="sxs-lookup"><span data-stu-id="c3e74-133">You can add containers in the **Files** page.</span></span>  
  
 <span data-ttu-id="c3e74-134">**Adicionar**</span><span class="sxs-lookup"><span data-stu-id="c3e74-134">**Add**</span></span>  
 <span data-ttu-id="c3e74-135">Adiciona uma nova linha em branco aos grupos de arquivos da listagem de grade do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="c3e74-135">Adds a new blank row to the grid listing filegroups for the database.</span></span>  
  
 <span data-ttu-id="c3e74-136">**Remover**</span><span class="sxs-lookup"><span data-stu-id="c3e74-136">**Remove**</span></span>  
 <span data-ttu-id="c3e74-137">Remove da grade a linha do grupo de arquivos selecionada.</span><span class="sxs-lookup"><span data-stu-id="c3e74-137">Removes the selected filegroup row from the grid.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c3e74-138">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="c3e74-138">See Also</span></span>  
 <span data-ttu-id="c3e74-139">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="c3e74-139">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span></span>  
 [<span data-ttu-id="c3e74-140">sys.databases &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="c3e74-140">sys.databases &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql)  
  
  
